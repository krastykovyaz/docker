FROM ubuntu
MAINTAINER lnoisomie
ENV LANG=C.UTF-8
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y ca-certificates \
	openssh-server \
	wget postfix
RUN apt-get update && apt-get install -y curl
RUN apt-get install -y git-core
RUN curl -s https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash

RUN rm -rf /var/lib/apt/lists/partial/*
RUN apt-get update
RUN apt-get clean


RUN apt-get install -y tzdata gitlab-ce

EXPOSE 443 22 80
ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && sleep 2 && gitlab-ctl reconfigure && tail -f /dev/null





#https://packages.gitlab.com/gitlab/gitlab-ce/install#bash-deb
#https://about.gitlab.com/install/#debian
#https://packages.gitlab.com/gitlab/gitlab-ce/packages/ubuntu/bionic/gitlab-ce_12.5.0-ce.0_amd64.deb


#docker build -t gitlabim .
#docker run -it --rm -p 8000:80 -p 8022:22 -p 8443:443 --privileged gitlabim
#docker image rm gitlabim

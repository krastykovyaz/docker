FROM ruby:2.5
MAINTAINER lnoisome
#ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install -y ruby ruby-bundler nodejs
RUN apt-get install curl
RUN mkdir /opt/app
WORKDIR /opt/app
RUN curl -S https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt update && apt -y install yarn
RUN curl  https://raw.github.com/railsgirls/installation-scripts/master/rails-install-fedora.sh | bash
RUN gem install rails
RUN cd .. && rails new app && cd app
WORKDIR /opt/app


#https://blog.codeship.com/running-rails-development-environment-docker/
#https://docs.docker.com/compose/rails/
#https://docs.docker.com/engine/reference/builder/
#https://guides.railsgirls.com/install

#inside ex02
#docker build -t 'ft-rails:on-build'  ./ft-rails
#inside ft-rails
#docker build -t 'cc'  .
#docker run --name cc -it -p 3000:3000 cc

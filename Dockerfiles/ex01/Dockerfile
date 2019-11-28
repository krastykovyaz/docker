FROM debian
MAINTAINER lnoisome
EXPOSE 9987/udp
EXPOSE 30033/tcp
EXPOSE 10011/tcp
RUN  apt-get update \
  && apt-get install -y wget bzip2 \
    && rm -rf /var/lib/apt/lists/*
WORKDIR ~/temp
RUN wget "https://files.teamspeak-services.com/releases/server/3.10.2/teamspeak3-server_linux_amd64-3.10.2.tar.bz2" && \
tar -vxjf ./teamspeak3-server_linux_amd64-3.10.2.tar.bz2
WORKDIR ./teamspeak3-server_linux_amd64
ENV TS3SERVER_LICENSE=accept
ENTRYPOINT sh ./ts3server_minimal_runscript.sh

#https://hub.docker.com/_/teamspeak
#https://docs.docker.com/engine/reference/builder/#/maintainer
#https://www.digitalocean.com/community/questions/tutorial-setup-teamspeak-server-debian-9-3
#https://stackoverflow.com/questions/28885137/how-to-run-wget-inside-ubuntu-docker-image
#docker run -p 9987:9987/udp -p 10011:10011/tcp -p 30033:30033/tcp <image>

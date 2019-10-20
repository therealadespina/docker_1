FROM debian
LABEL maintainer="adespina@student.21-school.ru" 
ENV TS3SERVER_LICENSE=accept
WORKDIR /home/teamspeak
EXPOSE 9987/udp 10011 30033
# The EXPOSE instruction informs Docker that the container listens on the specified network ports at runtime. You can specify whether the port listens on TCP or UDP, and the default is TCP if the protocol is not specified.
RUN apt-get update && \
    apt-get upgrade -y && \
	apt-get install -y wget bzip2 && \
	wget http://dl.4players.de/ts/releases/3.0.13.4/teamspeak3-server_linux_amd64-3.0.13.4.tar.bz2 && \
	tar -xvf teamspeak3-server_linux_amd64-3.0.13.4.tar.bz2
WORKDIR teamspeak3-server_linux_amd64
ENTRYPOINT sh ts3server_minimal_runscript.sh
# An ENTRYPOINT allows you to configure a container that will run as an executable.

# How to build it?
# docker build -t ex01 .

# How to run it?
# docker run -d --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01

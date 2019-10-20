FROM ubuntu:18.04
LABEL maintainer="adespina@student.21-school.ru"
RUN	apt-get update && \
	apt-get upgrade -y && \
	apt-get install -y ca-certificates openssh-server wget postfix
RUN apt-get update && apt-get install -y tzdata
RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && chmod 777 script.deb.sh && ./script.deb.sh && apt-get install -y gitlab-ce
EXPOSE 443 22 80
ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null

# How to build it?
# docker build -t ex03 .

# How to run it?
# docker run -d -it --rm --name gitlab -p 8080:80 -p 8022:22 -p 8443:443 --privileged ex03

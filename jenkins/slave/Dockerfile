FROM ubuntu:14.04

MAINTAINER Fai Fung <ffung@xebia.com>

RUN apt-get update
RUN apt-get -y install openssh-server
RUN apt-get -y install openjdk-7-jdk

RUN mkdir /var/run/sshd
RUN useradd -m jenkins
RUN usermod -p $(echo jenkins | openssl passwd -1 -stdin) jenkins

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]

FROM ubuntu:14.04

MAINTAINER Fai Fung <ffung@xebia.com>

RUN apt-get update
RUN apt-get -y install wget
RUN apt-get -y install unzip
RUN apt-get -y install openjdk-7-jdk
RUN apt-get -y install sudo
RUN useradd -m teamcity

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64

ADD setup-agent.sh /home/teamcity/setup-agent.sh

EXPOSE 9090
CMD sudo -H -u teamcity -s -- sh -c "JAVA_HOME=$JAVA_HOME; TEAMCITY_SERVER=$TEAMCITY_SERVER bash /home/teamcity/setup-agent.sh run"

FROM ubuntu:14.04

MAINTAINER Fai Fung <ffung@xebia.com>

VOLUME  ["/data/teamcity"]
ENV TEAMCITY_DATA_PATH /data/teamcity

RUN apt-get update
RUN apt-get -y install wget
RUN apt-get -y install openjdk-7-jdk
RUN wget -qO- http://download.jetbrains.com/teamcity/TeamCity-8.1.4.tar.gz | tar xz -C /opt

# Adds the Team City Vagrant/Docker plugin, allowing vagrant/docker build steps (so they are not used as Build Agents)
ADD plugins/TeamCity.Virtual.zip /data/teamcity/plugins/

EXPOSE 8111
CMD ["/opt/TeamCity/bin/teamcity-server.sh", "run"]

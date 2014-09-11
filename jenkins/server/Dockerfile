FROM jenkins

MAINTAINER Fai Fung <ffung@xebia.com>

VOLUME ["/var/jenkins_home"]

USER root
RUN mkdir -p /var/jenkins_plugins && chown jenkins /var/jenkins_plugins
ADD https://updates.jenkins-ci.org/download/plugins/docker-plugin/0.7/docker-plugin.hpi /var/jenkins_plugins/
RUN chown jenkins /var/jenkins_plugins/*

CMD rsync -a /var/jenkins_plugins/ /var/jenkins_home/plugins/ && /usr/local/bin/jenkins.sh

ci-docker
=========

Continuous Integration using Docker


## Build/running the Teamcity images
###Server
```
$cd teamcity/server
$docker build -t teamcity-server .
$docker run -p 8111:8111 --net=host teamcity-server
```

###Agent 
```
$cd teamcity/agent
$docker build -t teamcity-agent .
$docker run -e TEAMCITY_SERVER=http://192.168.59.103:8111 -P teamcity-agent
```

## Build/running the Jenkins images
###Server
```
$cd jenkins/server
$docker build -t jenkins-server .
$docker run -p 8081:8080 -v /var/jenkins_home:/var/jenkins_home  jenkins-server
```
###Agent 
```
$cd jenkins/slave
$docker build -t jenkins-slave .
$docker run jenkins-slave
```
Note: Manually starting slave isn't required, it will be started by the Jenkins Server via the Docker plugin


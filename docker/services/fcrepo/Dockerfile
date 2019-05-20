FROM tomcat:8.0-jre8

MAINTAINER oliverar/fcrepo

RUN apt-get update && apt-get -y upgrade

ARG FEDORA_TAG=5.0.2

ENV CATALINA_HOME="/usr/local/tomcat" \
    PATH="$CATALINA_HOME/bin:$PATH" \
		JAVA_OPTS="-Dfcrepo.modeshape.configuration=classpath:/config/file-simple/repository.json -Dfcrepo.home=/mnt/fcrepo-data -Dfcrepo.audit.container=/mnt/audit"

RUN mkdir /mnt/ingest
RUN mkdir /mnt/audit

RUN sed -i '$i<role rolename="fedoraUser"/>$i<role rolename="fedoraAdmin"/>$i<role rolename="manager-gui"/>$i<user username="testuser" password="password1" roles="fedoraUser"/>$i<user username="adminuser" password="password2" roles="fedoraUser"/>$i<user username="fedoraAdmin" password="secret3" roles="fedoraAdmin"/>$i<user username="fedora4" password="fedora4" roles="manager-gui"/>' /usr/local/tomcat/conf/tomcat-users.xml

RUN cd /tmp \
	&& curl -fSL https://github.com/fcrepo4/fcrepo4/releases/download/fcrepo-$FEDORA_TAG/fcrepo-webapp-$FEDORA_TAG.war -o fcrepo.war \
	&& cp fcrepo.war /usr/local/tomcat/webapps/fcrepo.war

WORKDIR /usr/local/tomcat

EXPOSE 8080

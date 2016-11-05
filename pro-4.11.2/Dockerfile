FROM jfrog-docker-reg2.bintray.io/jfrog/artifactory-pro:4.11.2
MAINTAINER Venkatesh Amudhan (venkatesh@ticketfly.com)

RUN yum install -y tar

ADD http://cdn.mysql.com/Downloads/Connector-J/mysql-connector-java-5.1.39.tar.gz /tmp/mysql-connector-java-5.1.39.tar.gz
RUN cd /tmp; tar zxf mysql-connector-java-5.1.39.tar.gz; cp /tmp/mysql-connector-java-5.1.39/mysql-connector-java-5.1.39-bin.jar /var/opt/jfrog/artifactory/tomcat/lib

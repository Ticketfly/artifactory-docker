FROM jfrog-docker-reg2.bintray.io/jfrog/artifactory-registry:4.7.6
MAINTAINER Patrick Tescher <pat2man@gmail.com>

RUN yum install -y tar

ADD http://cdn.mysql.com/Downloads/Connector-J/mysql-connector-java-5.1.38.tar.gz /tmp/mysql-connector-java-5.1.38.tar.gz
RUN cd /tmp; tar zxf mysql-connector-java-5.1.38.tar.gz; cp /tmp/mysql-connector-java-5.1.38/mysql-connector-java-5.1.38-bin.jar /var/opt/jfrog/artifactory/tomcat/lib

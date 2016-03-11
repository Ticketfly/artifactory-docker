FROM jfrog-docker-reg2.bintray.io/jfrog/artifactory-registry:4.5.2
MAINTAINER Patrick Tescher <pat2man@gmail.com>

ENV MYSQL_DRIVER_VERSION=5.1.38

ADD http://cdn.mysql.com/Downloads/Connector-J/mysql-connector-java-$MYSQL_DRIVER_VERSION.tar.gz /tmp

RUN yum install -y tar && \
    cd /tmp && \
    tar zxf mysql-connector-java-$MYSQL_DRIVER_VERSION.tar.gz && \
    cp /tmp/mysql-connector-java-$MYSQL_DRIVER_VERSION/mysql-connector-java-$MYSQL_DRIVER_VERSION-bin.jar /var/opt/jfrog/artifactory/tomcat/lib && \
    rm -r /tmp/mysql-connector-java-* && \
    yum remove -y tar

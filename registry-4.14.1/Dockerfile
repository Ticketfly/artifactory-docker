FROM jfrog-docker-reg2.bintray.io/jfrog/artifactory-registry:4.14.1
MAINTAINER Venkatesh Amudhan <venkatesh@ticketfly.com>

RUN yum install -y tar

ADD http://cdn.mysql.com/Downloads/Connector-J/mysql-connector-java-5.1.39.tar.gz /tmp/mysql-connector-java-5.1.39.tar.gz
RUN cd /tmp; tar zxf mysql-connector-java-5.1.39.tar.gz; cp /tmp/mysql-connector-java-5.1.39/mysql-connector-java-5.1.39-bin.jar /var/opt/jfrog/artifactory/tomcat/lib

RUN curl -L --cookie "gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/8u91-b14/jre-8u91-linux-x64.rpm" > jre-8u91-linux-x64.rpm; rpm -i jre-8u91-linux-x64.rpm

COPY newrelic-java-3.33.0.zip /tmp/newrelic.zip
RUN yum install -y unzip && \
  unzip /tmp/newrelic.zip -d /opt/jfrog/artifactory/tomcat

CMD java -jar /opt/jfrog/artifactory/tomcat/newrelic/newrelic.jar install && \
  chown -R artifactory: /opt/jfrog/artifactory/tomcat/newrelic && \
  /tmp/run.sh

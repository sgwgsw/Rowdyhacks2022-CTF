FROM tomcat:8.0.53-jre8

WORKDIR /tmp

RUN wget https://raw.githubusercontent.com/sgwgsw/tomcat-log4j2/main/log4j2.xml
RUN wget https://raw.githubusercontent.com/sgwgsw/tomcat-log4j2/main/server.xml
RUN wget https://raw.githubusercontent.com/sgwgsw/tomcat-log4j2/main/setenv.sh
RUN wget https://raw.githubusercontent.com/sgwgsw/tomcat-log4j2/main/web.xml

RUN rm /usr/local/tomcat/conf/logging.properties
RUN mv log4j2.xml /usr/local/tomcat/conf
RUN mv server.xml /usr/local/tomcat/conf
RUN mv setenv.sh /usr/local/tomcat/bin
RUN mv web.xml /usr/local/tomcat/conf
RUN chmod u+x /usr/local/tomcat/bin/setenv.sh

RUN wget https://repo1.maven.org/maven2/org/apache/tomcat/tomcat-juli/8.0.53/tomcat-juli-8.0.53.jar
RUN mv tomcat-juli-8.0.53.jar /usr/local/tomcat/bin/tomcat-juli.jar

RUN wget https://repo1.maven.org/maven2/org/apache/tomcat/extras/tomcat-extras-juli-adapters/8.0.53/tomcat-extras-juli-adapters-8.0.53.jar
RUN mv tomcat-extras-juli-adapters-8.0.53.jar /usr/local/tomcat/lib/tomcat-juli-adapters.jar


RUN wget https://archive.apache.org/dist/logging/log4j/2.14.0/apache-log4j-2.14.0-bin.tar.gz
RUN tar -xvzf apache-log4j-2.14.0-bin.tar.gz
RUN mv apache-log4j-2.14.0-bin/log4j-api-2.14.0.jar /usr/local/tomcat/lib
RUN mv apache-log4j-2.14.0-bin/log4j-core-2.14.0.jar /usr/local/tomcat/lib
RUN mv apache-log4j-2.14.0-bin/log4j-jul-2.14.0.jar /usr/local/tomcat/lib
RUN rm apache-log4j-2.14.0-bin.tar.gz

EXPOSE 8080

CMD ["catalina.sh", "run"]

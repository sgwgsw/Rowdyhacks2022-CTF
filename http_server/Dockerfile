FROM alpine:latest

RUN apk update
ENV PYTHONUNBUFFERED=1
RUN apk add --update --no-cache python3 && ln -sf python3 /usr/bin/python
RUN python3 -m ensurepip
RUN pip3 install --no-cache --upgrade pip setuptools
RUN apk add tcpdump

#RUN apk add openjdk11

RUN apk add git

RUN cd opt &&\
    git clone https://github.com/sgwgsw/Log4Shell_PoC.git

#RUN cd /opt/Log4Shell_PoC/exploit &&\
#    python3 -m http.server 8889

WORKDIR /opt/Log4Shell_PoC/exploit

CMD ["python3", "-m", "http.server", "8889"]

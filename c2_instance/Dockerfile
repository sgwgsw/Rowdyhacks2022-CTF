FROM alpine:latest

RUN apk update
RUN apk add --no-cache netcat-openbsd
RUN apk add --no-cache curl

ENTRYPOINT ["tail", "-f", "/dev/null"]

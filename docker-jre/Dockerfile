FROM alpine
MAINTAINER shajalahamedcse@gmail.com

ENV JAVA_HOME=/usr/lib/jvm/default-jvm/jre

RUN apk upgrade --update-cache
RUN apk add openjdk8-jre

RUN rm -rf /tmp/* /var/cache/apk/*

CMD ["java", "-version"]
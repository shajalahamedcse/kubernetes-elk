FROM shajalahamedcse/docker-jre:latest

MAINTAINER shajalahamedcse@gmail.com

ENV LOGSTASH_PKG_NAME logstash-5.1.2


RUN apk add --update curl bash ca-certificates


# Install Logstash
RUN cd /
RUN curl -Ls -o $LOGSTASH_PKG_NAME.tar.gz https://artifacts.elastic.co/downloads/logstash/$LOGSTASH_PKG_NAME.tar.gz
RUN tar zxf $LOGSTASH_PKG_NAME.tar.gz
RUN mv $LOGSTASH_PKG_NAME /logstash
RUN rm -f $LOGSTASH_PKG_NAME.tar.gz

 # Logstash config
ADD ./config/logstash.conf /logstash/conf/logstash.conf

 # Certificates for logstash-forwarders
#ADD certs/logstash-forwarder.crt /logstash/certs/logstash-forwarder.crt
#ADD certs/logstash-forwarder.key /logstash/certs/logstash-forwarder.key

CMD ["/logstash/bin/logstash", "-f", "/conf/logstash.conf"]
# https://github.com/elastic/logstash-docker
FROM docker.elastic.co/logstash/logstash:7.8.0
# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json

USER root

RUN yum update -y && yum install -y wget

ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

CMD dockerize -timeout 5m -wait tcp://rabbitmq:5672 -wait tcp://elasticsearch:9200
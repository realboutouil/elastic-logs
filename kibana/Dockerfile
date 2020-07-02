# https://github.com/elastic/kibana-docker
FROM docker.elastic.co/kibana/kibana:7.8.0
# Add your kibana plugins setup here
# Example: RUN kibana-plugin install <name|url>
RUN yum update -y && yum install -y wget

ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

CMD dockerize -timeout 5m -wait tcp://rabbitmq:5672 -wait tcp://elasticsearch:9200 -wait tcp://logstash:35000
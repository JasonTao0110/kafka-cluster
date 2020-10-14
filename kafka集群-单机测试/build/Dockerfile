From centos:7.6.1810

COPY ./jdk-11.0.8_linux-x64_bin.rpm /opt/install/
COPY ./kafka_2.13-2.6.0.tgz /opt/install/

WORKDIR /opt/install

RUN rpm -ivh jdk-11.0.8_linux-x64_bin.rpm \
    && tar zxvf kafka_2.13-2.6.0.tgz \
    && mv kafka_2.13-2.6.0 /usr/local/kafka/


WORKDIR /usr/local/kafka

# Use "exec" form so that it runs as PID 1 (useful for graceful shutdown)
CMD ["./bin/kafka-server-start.sh", "config/server.properties"]

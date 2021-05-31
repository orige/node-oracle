FROM node:14-slim

# hadolint ignore=DL3008
RUN apt-get update && \
    apt-get install -yq wget unzip libaio1 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN mkdir -p /opt/oracle

WORKDIR /opt/oracle

RUN wget https://download.oracle.com/otn_software/linux/instantclient/instantclient-basic-linuxx64.zip && \
    unzip instantclient-basic-linuxx64.zip && \
    rm -f instantclient-basic-linuxx64.zip && \
    cd instantclient* && \
    echo /opt/oracle/instantclient* > /etc/ld.so.conf.d/oracle-instantclient.conf && \
    ldconfig

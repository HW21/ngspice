
# NGSPICE in Alpine Linux 

FROM alpine:latest

ENV NGSPICE_VERSION 33

RUN apk add --no-cache --virtual .build-deps \
    autoconf automake bison curl flex g++ libx11-dev libxaw-dev libtool make

RUN curl -fSL https://github.com/imr/ngspice/archive/ngspice-$NGSPICE_VERSION.tar.gz -o ngspice.tar.gz \
    && mkdir -p /usr/src \
    && tar -zxC /usr/src -f ngspice.tar.gz \
    && rm ngspice.tar.gz \
    && cd /usr/src/ngspice-ngspice-$NGSPICE_VERSION \
    && ./autogen.sh \
    && ./configure \
    && make \
    && make install


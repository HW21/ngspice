
# NGSPICE in Centos 8 

FROM centos:8 
ENV NGSPICE_VERSION 33
RUN yum install -y make gdb gcc bison flex libtool autoconf automake gcc libX11 libX11-devel libXaw libXaw-devel readline readline-devel && \
    curl -fSL https://github.com/imr/ngspice/archive/ngspice-$NGSPICE_VERSION.tar.gz -o ngspice.tar.gz && \
    mkdir -p /usr/src  && \
    tar -zxC /usr/src -f ngspice.tar.gz && \
    cd /usr/src/ngspice-ngspice-$NGSPICE_VERSION     && \
    ./autogen.sh     && \
    mkdir -p debug && \
    cd debug && \
    ../configure --with-readline=yes CFLAGS="-g -m64 -O0 -Wall -Wno-unused-but-set-variable -std=c99" LDFLAGS="-m64 -g" --disable-dependency-tracking && \
    make && \
    make install 


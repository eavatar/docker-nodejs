from ubuntu:14.04.1

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update
RUN apt-get install -y curl

RUN mkdir -p /dist/opt /dist/lib /dist/usr/lib
RUN curl -s http://nodejs.org/dist/v0.10.36/node-v0.10.36-linux-x64.tar.gz | gunzip | tar -xf - -C /dist/opt
RUN mv /dist/opt/node-v0.10.36-linux-x64 /dist/opt/node


WORKDIR /dist
RUN rm -rf opt/node/share/man  \
           opt/node/lib/node_modules/npm/man \
           opt/node/lib/node_modules/npm/doc

RUN \
    cp /lib/x86_64-linux-gnu/libssl.so.1.0.0 lib/ &&\
    cp /lib/x86_64-linux-gnu/libcrypto.so.1.0.0 lib &&\
    cp /usr/lib/x86_64-linux-gnu/libstdc++.so.6 usr/lib/ &&\
    cp /lib/x86_64-linux-gnu/libgcc_s.so.1 lib/

RUN tar cf /overlayfs.tar .

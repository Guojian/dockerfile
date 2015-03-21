FROM resin/rpi-raspbian:wheezy-2015-03-18

RUN apt-get update

RUN apt-get install -y tar wget python automake make gcc g++

RUN cd /tmp && \
  wget http://nodejs.org/dist/node-latest.tar.gz && \
  tar zxvf node-latest.tar.gz

RUN cd /tmp/node-v0.12.0 && ls -l && ./configure && make && make install

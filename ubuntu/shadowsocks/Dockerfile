FROM ubuntu:14.04.1
MAINTAINER guojian <k@yooo.io>

RUN apt-get update && \
    apt-get install -y python-pip python-m2crypto git && \
    pip install "git+http://github.com/menghan/shadowsocks.git@master" && \
    apt-get purge -y python-pip python-m2crypto+ git python-pkg-resources+ && \
    apt-get autoremove -y && \
    apt-get clean

ADD shadowsocks.json /etc/

USER nobody

ENTRYPOINT ["/usr/local/bin/ssserver", "-c", "/etc/shadowsocks.json"]

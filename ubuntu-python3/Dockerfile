FROM ubuntu:latest
MAINTAINER ziyue 

ENV http_proxy "http://docker.for.mac.localhost:1087/"
ENV HTTP_PROXY "http://docker.for.mac.localhost:1087/"
ENV https_proxy "http://docker.for.mac.localhost:1087/"
ENV HTTPS_PROXY "http://docker.for.mac.localhost:1087/"
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
  && apt-get install -y python3-pip \
  && cd /usr/local/bin \
  && ln -s /usr/bin/python3 python \
  && pip3 --no-cache-dir install --upgrade pip \
  && rm -rf /var/lib/apt/lists/*


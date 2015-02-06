# Build:
#   docker build -t nocquidant/git .
#
# Run:
#   docker run --rm  nocquidant/git version
#   docker run --rm -v `pwd`:/src nocquidant/git clone https://github.com/nocquidant/my-spring-boot-sample.git
#   alias dgit='docker run --rm -v `pwd`:/src nocquidant/git'

FROM ubuntu:14.10
MAINTAINER Nicolas Ocquidant <nocquidant@gmail.com>

ENV http_proxy http://proxy-nantes.groupesigma.fr:8080 
ENV https_proxy http://proxy-nantes.groupesigma.fr:8080 
ENV no_proxy 127.0.0.1,localhost,.groupesigma.fr

RUN \ 
  apt-get update && \
  apt-get install -y git=1:2.1.0-1

VOLUME ["/src"]
WORKDIR /src

ENTRYPOINT ["/usr/bin/git"]

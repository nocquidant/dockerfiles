# Build:
#   docker build -t nocquidant/cowsay .
#
# Run:
#   docker run --rm  nocquidant/cowsay

FROM ubuntu:latest
MAINTAINER Nicolas Ocquidant <nocquidant@gmail.com>

ENV http_proxy http://proxy-nantes.groupesigma.fr:8080 
ENV https_proxy http://proxy-nantes.groupesigma.fr:8080 
ENV no_proxy 127.0.0.1,localhost,.groupesigma.fr

RUN apt-get update
RUN apt-get install -y cowsay fortune

ENV PATH $PATH:/usr/games

ENTRYPOINT fortune | cowsay

# ADD ./duck.cow /duck.cow
# ENTRYPOINT fortune | cowsay -f /duck.cow

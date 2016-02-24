# Build:
#   docker build -t nocquidant/java8 .

FROM ubuntu:latest

#
# Install wget
#

RUN \
  apt-get -y update && \
  apt-get -y install wget && \
  rm -rf /var/lib/apt/lists/*

#
# Install Java 8u74
#

RUN mkdir -p /opt/jdk

WORKDIR /opt/jdk

RUN \
  wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u74-b02/jdk-8u74-linux-x64.tar.gz \
  && tar -zxf jdk-8u74-linux-x64.tar.gz \
  && rm -f jdk-8u74-linux-x64.tar.gz
 
RUN \
  update-alternatives --install /usr/bin/java java /opt/jdk/jdk1.8.0_74/bin/java 100 \
  && update-alternatives --install /usr/bin/javac javac /opt/jdk/jdk1.8.0_74/bin/javac 100

#
# Set env variable
#  

ENV JAVA_HOME /opt/jdk/jdk1.8.0_74

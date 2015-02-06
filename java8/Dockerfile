FROM ubuntu:14.04.1

ENV http_proxy http://proxy-nantes.groupesigma.fr:8080 
ENV https_proxy http://proxy-nantes.groupesigma.fr:8080 
ENV no_proxy 127.0.0.1,localhost,.groupesigma.fr

#
# Install wget
#

RUN \
  apt-get -y update && \
  apt-get -y install wget && \
  rm -rf /var/lib/apt/lists/*

#
# Install Java 8u31
#

RUN mkdir -p /opt/jdk

WORKDIR /opt/jdk

RUN \
  wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u31-b13/jdk-8u31-linux-x64.tar.gz \
  && tar -zxf jdk-8u31-linux-x64.tar.gz \
  && rm -f jdk-8u31-linux-x64.tar.gz
 
RUN \
  update-alternatives --install /usr/bin/java java /opt/jdk/jdk1.8.0_31/bin/java 100 \
  && update-alternatives --install /usr/bin/javac javac /opt/jdk/jdk1.8.0_31/bin/javac 100

#
# Set env variable
#  

ENV JAVA_HOME /opt/jdk/jdk1.8.0_31

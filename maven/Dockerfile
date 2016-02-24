# Build:
#   docker build -t nocquidant/maven .

FROM nocquidant/java8

ARG --description="Java http.proxyHost" proxy_host
ARG --description="Java http.proxyPort" proxy_port
ARG --description="Java http.proxyUser" proxy_user
ARG --description="Java http.proxyPassword" proxy_password
ARG --description="Java http.nonProxyHosts" non_proxy_hosts

#
# Install curl
#

RUN \
  apt-get -y update && \
  apt-get -y install curl && \
  rm -rf /var/lib/apt/lists/*

#
# Install Maven
#

ENV MAVEN_VERSION 3.2.5

RUN \
  curl -sSL http://archive.apache.org/dist/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz | tar xzf - -C /usr/share \
  && mv /usr/share/apache-maven-$MAVEN_VERSION /usr/share/maven \
  && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
  
#
# Maven config
#

ENV MAVEN_OPTS "\
  -Dhttp.proxyHost=$proxy_host -Dhttp.proxyPort=$proxy_port \
  -Dhttp.proxyUser=$proxy_user -Dhttp.proxyPassword=$proxy_password \
  -Dhttp.nonProxyHosts=$non_proxy_hosts \
  -Dhttps.proxyHost=$proxy_host -Dhttps.proxyPort=$proxy_port \
  -Dhttps.proxyUser=$proxy_user -Dhttps.proxyPassword=$proxy_password \
  -Dhttps.nonProxyHosts=$non_proxy_hosts"

#
# Set env variable
#  

ENV MAVEN_HOME /usr/share/maven

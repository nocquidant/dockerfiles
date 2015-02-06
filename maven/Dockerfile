FROM nocquidant/java8

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

ENV MAVEN_OPTS "$MAVEN_OPTS -Dhttp.proxyHost=proxy-nantes.groupesigma.fr -Dhttp.proxyPort=8080"
ENV MAVEN_OPTS "$MAVEN_OPTS -Dhttp.nonProxyHosts=127.0.0.1|localhost|*.groupesigma.fr|*.devsopra.com"
ENV MAVEN_OPTS "$MAVEN_OPTS -Dhttps.proxyHost=proxy-nantes.groupesigma.fr -Dhttps.proxyPort=8080"
ENV MAVEN_OPTS "$MAVEN_OPTS -Dhttps.nonProxyHosts=127.0.0.1|localhost|*.groupesigma.fr|*.devsopra.com"

#
# Set env variable
#  

ENV MAVEN_HOME /usr/share/maven

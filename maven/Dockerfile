FROM nocquidant/java8

# ENV http_proxy http://proxy-nantes.groupesigma.fr:8080 
# ENV https_proxy http://proxy-nantes.groupesigma.fr:8080 
# ENV no_proxy 127.0.0.1,localhost,.groupesigma.fr

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
# Set env variable
#  

ENV MAVEN_HOME /usr/share/maven
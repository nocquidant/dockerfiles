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

RUN mv /usr/share/maven/conf/settings.xml /usr/share/maven/conf/settings.xml.OLD
COPY ./conf/settings.xml /usr/share/maven/conf/settings.xml

#
# Set env variable
#  

ENV MAVEN_HOME /usr/share/maven

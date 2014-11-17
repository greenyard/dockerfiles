FROM debian:wheezy
MAINTAINER atomi <http:/twitter.com/atomi>

RUN \
  echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee -a /etc/apt/sources.list && \
  echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee -a /etc/apt/sources.list && \
  apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886

RUN \
  apt-get update -y && \
  echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
  apt-get install -yq --no-install-recommends ca-certificates oracle-java7-installer && \
  apt-get clean && \
  rm -rf \
  	/var/lib/apt/lists/* \
  	/tmp/* \
  	/var/tmp/* \
  	/var/cache/man/* \
  	/var/cache/apt/* \
  	/usr/share/doc/* \
  	/usr/share/info/* \
  	/usr/share/man/*

RUN echo "JAVA_HOME=/usr/lib/jvm/java-7-oracle" >> /etc/environment

FROM atomi/wheezy-oraclejdk:8

ENV GRADLE_HOME /usr/local
ENV GRADLE_VERSION 2.2

# zip
RUN \
  apt-get update -y && \
  apt-get install -yq --no-install-recommends zip unzip && \
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

RUN wget https://services.gradle.org/distributions/gradle-$GRADLE_VERSION-bin.zip && \
    unzip gradle*.zip && \
    cp -r gradle*/* /usr/local && \
    rm gradle* -rf

WORKDIR /data

FROM atomi/wheezy-oracle-jdk:8

ENV GROOVY_HOME /usr/local
ENV GROOVY_VERSION 2.3.7

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

RUN wget http://dl.bintray.com/groovy/maven/groovy-binary-$GROOVY_VERSION.zip && \
    unzip groovy*.zip && \
    cp -r groovy*/* /usr/local && \
    rm groovy* -rf

WORKDIR /data
ENTRYPOINT ["groovy"]

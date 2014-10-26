FROM atomi/wheezy-oracle-jdk:8
MAINTAINER atomi <http:/twitter.com/atomi>

ENV RESIN_VERSION 4.0.41
ENV RESIN_HOME /resin

# Install certs and tools and remove cache
RUN apt-get update && \
    apt-get install -yq --no-install-recommends pwgen ca-certificates && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install Jetty TODO: check md5
RUN mkdir $RESIN_HOME && \
		wget -O - http://caucho.com/download/resin-$RESIN_VERSION.tar.gz | tar xvzf - -C $RESIN_HOME

EXPOSE 8080
CMD ["$RESIN_HOME/bin/resin.sh", "console"]

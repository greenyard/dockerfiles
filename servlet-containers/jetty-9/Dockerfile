FROM atomi/wheezy-oracle-jdk:8
MAINTAINER atomi <http:/twitter.com/atomi>

ENV JETTY_VERSION 9.2.3.v20140905
ENV JETTY_HOME /jetty

# Install CA certs
RUN apt-get update -y && \
    apt-get install -yq --no-install-recommends ca-certificates && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install Jetty TODO: check md5
RUN wget -O - http://download.eclipse.org/jetty/$JETTY_VERSION/dist/jetty-distribution-$JETTY_VERSION.tar.gz /opt/jetty.tar.gz | tar xzf -
RUN mv jetty-distribution-$JETTY_VERSION $JETTY_HOME

VOLUME $JETTY_HOME/webapps/ROOT

EXPOSE 8080
CMD ["$JETTY_HOME/bin/jetty.sh", "run"]

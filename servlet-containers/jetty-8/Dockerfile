FROM atomi/wheezy-oracle-jdk:8
MAINTAINER atomi <http:/twitter.com/atomi>

ENV JETTY_VERSION 8.1.16.v20140903
ENV JETTY_HOME /jetty

# Install Jetty TODO: check md5
RUN mkdir -p $JETTY_HOME && \
		wget -O - http://download.eclipse.org/jetty/$JETTY_VERSION/dist/jetty-distribution-$JETTY_VERSION.tar.gz /opt/jetty.tar.gz | tar xzf - -C $JETTY_HOME --strip-components=1

EXPOSE 8080
CMD ["$JETTY_HOME/bin/jetty.sh", "run"]

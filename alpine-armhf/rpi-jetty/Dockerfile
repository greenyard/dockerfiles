FROM atomi/rpi-alpine

ENV JETTY_HOME=/usr/share/jetty JETTY_VERSION=9.2.13.v20150730

RUN apk --update add \
          openjdk7-jre \
          bash \
          tar \
    && mkdir -p $JETTY_HOME \
    && wget -O - http://download.eclipse.org/jetty/$JETTY_VERSION/dist/jetty-distribution-$JETTY_VERSION.tar.gz | tar xzf - -C $JETTY_HOME --strip-components=1 \
    && ln -sf $JETTY_HOME/webapps /data

VOLUME /data
EXPOSE 8080
CMD $JETTY_HOME/bin/jetty.sh run

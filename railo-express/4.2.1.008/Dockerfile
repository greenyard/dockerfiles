FROM atomi/wheezy-oracle-jdk:8

ENV RAILO_VERSION 4.2.1.008
ENV RAILO_HOME /railo

# Download and untar railo express
RUN \
		mkdir $RAILO_HOME && \
		wget -O - http://www.getrailo.org/down.cfm?item=/railo/remote/download42/$RAILO_VERSION/railix/linux/railo-express-$RAILO_VERSION-nojre.tar.gz | tar zxf - -C $RAILO_HOME --strip-components=1

EXPOSE 8888
CMD ["$RAILO_HOME/start"]

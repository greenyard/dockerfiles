FROM atomi/tomcat:7.0.56-wheezy-oraclejdk8

ENV RAILO_VERSION 4.2.1.008
ENV CATALINA_OPTS -javaagent:$CATALINA_HOME/lib/railo-inst.jar

# Download and untar Railo jars
RUN wget --no-verbose -O - http://www.getrailo.org/down.cfm?item=/railo/remote/download42/$RAILO_VERSION/custom/all/railo-$RAILO_VERSION-jars.tar.gz | tar zxf - -C $CATALINA_HOME/lib --strip-components=1

CMD $CATALINA_HOME/bin/catalina.sh run

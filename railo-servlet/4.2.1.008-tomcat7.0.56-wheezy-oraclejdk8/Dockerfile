FROM atomi/tomcat:7.0.56-wheezy-oraclejdk8

ENV RAILO_VERSION 4.2.1.008

ENV RAILO_HOME /railo
ENV RAILO_LIB $RAILO_HOME/lib

ENV CATALINA_OPTS -javaagent:$RAILO_LIB/railo-inst.jar

# Download and untar Railo jars
RUN mkdir -p $RAILO_LIB && \
		wget --no-verbose -O - http://www.getrailo.org/down.cfm?item=/railo/remote/download42/$RAILO_VERSION/custom/all/railo-$RAILO_VERSION-jars.tar.gz | tar zxf - -C $RAILO_LIB --strip-components=1

# Add Railo jars to common.loader in catalina.properties
RUN sed -i -e 's:^\(common.loader=${catalina.base}/lib,${catalina.base}/lib/\*\.jar,${catalina.home}/lib,${catalina.home}/lib/\*\.jar$\):\1',"$RAILO_LIB/*\.jar:" \
		$CATALINA_HOME/conf/catalina.properties

RUN ln -s $CATALINA_HOME/webapps/ROOT /data

# Clean out ROOT and add our workspace
WORKDIR /data
ONBUILD RUN rm -rf *
ONBUILD ADD . /data/

EXPOSE 8080

CMD $CATALINA_HOME/bin/catalina.sh run

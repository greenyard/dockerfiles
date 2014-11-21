FROM atomi/wheezy-oracle-jdk:8
MAINTAINER atomi <http:/twitter.com/atomi>

ENV TOMCAT_MAJOR_VERSION 7
ENV TOMCAT_MINOR_VERSION 7.0.56
ENV CATALINA_HOME /tomcat

# Install Tomcat
RUN wget -q https://archive.apache.org/dist/tomcat/tomcat-$TOMCAT_MAJOR_VERSION/v$TOMCAT_MINOR_VERSION/bin/apache-tomcat-$TOMCAT_MINOR_VERSION.tar.gz && \
    wget -qO- https://archive.apache.org/dist/tomcat/tomcat-$TOMCAT_MAJOR_VERSION/v$TOMCAT_MINOR_VERSION/bin/apache-tomcat-$TOMCAT_MINOR_VERSION.tar.gz.md5 | md5sum -c - && \
    tar zxf apache-tomcat-*.tar.gz && \
    rm apache-tomcat-*.tar.gz && \
    mv apache-tomcat* $CATALINA_HOME

# Remove management, config and documentations contexts but keep ROOT
RUN find $CATALINA_HOME/webapps/* ! -name 'ROOT' -type d -exec rm -rf {} +

EXPOSE 8080

CMD $CATALINA_HOME/bin/catalina.sh run

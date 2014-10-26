FROM debian:wheezy
MAINTAINER atomi <http:/twitter.com/atomi>
RUN alias c="clear" && alias ll="ls -lha"

ENV NODEJS_VERSION 0.10.31

RUN apt-get update -y && \
		apt-get install --no-install-recommends -yq curl python build-essential ca-certificates

RUN mkdir /nodejs && \ 
		curl http://nodejs.org/dist/v$NODEJS_VERSION/node-v$NODEJS_VERSION-linux-x64.tar.gz | tar xvzf - -C /nodejs --strip-components=1

ENV PATH $PATH:/nodejs/bin

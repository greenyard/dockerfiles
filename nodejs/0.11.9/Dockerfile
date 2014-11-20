FROM debian:wheezy

RUN gpg --keyserver pgp.mit.edu --recv-keys 7937DFD2AB06298B2293C3187D33FF9D0246406D

ENV NODE_VERSION 0.11.9
ENV NPM_VERSION 2.1.7

RUN apt-get update && \
		apt-get install --no-install-recommends -yq curl build-essential && \
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

RUN curl -SLO "http://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.gz" && \
    curl -SLO "http://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc" && \
	  gpg --verify SHASUMS256.txt.asc && \
	  grep " node-v$NODE_VERSION-linux-x64.tar.gz\$" SHASUMS256.txt.asc | sha256sum -c - && \
	  tar -xzf "node-v$NODE_VERSION-linux-x64.tar.gz" -C /usr/local --strip-components=1 && \
	  rm "node-v$NODE_VERSION-linux-x64.tar.gz" SHASUMS256.txt.asc
	  
RUN npm install -g npm@"$NPM_VERSION" && \
	  npm cache clear

FROM atomi/node

RUN apt-get update && \
		apt-get install -yq \
			haskell-platform node \
			libghc-terminfo-dev \
		apt-get clean && \
		rm -rf \ 
		  /var/lib/apt/lists/* \
		  /tmp/*

# cabal install elm-reactor # not working
RUN	cabal update && \
		cabal install cabal-install && \
		cabal install elm elm-repl elm-get

RUN bash -c "ln -s /root/.cabal/bin/{elm,elm-doc,elm-get,elm-repl} /usr/local/bin/"

FROM debian:wheezy

RUN apt-get update && \
		apt-get install -yq curl haskell-platform node libghc-terminfo-dev git && \
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

RUN	cabal update && \
		cabal install cabal-install && \
		cabal install elm elm-repl elm-get

#   cabal install elm-reactor # not working

RUN bash -c "ln -s /root/.cabal/bin/{elm,elm-doc,elm-get,elm-repl} /usr/local/bin/"

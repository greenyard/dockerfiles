FROM atomi/node

ENV HASKELL_PLATFORM_VERSION 2014.2.0.0

# testing cabal needs at least GLIBC_2.14 libc6-dev
RUN echo "deb http://http.us.debian.org/debian/ testing non-free contrib main" | tee -a /etc/apt/sources.list && \
    apt-get update && \
    apt-get install -y zlib1g-dev libgmp10 libghc-terminfo-dev && \
    rm -rf \ 
      /var/lib/apt/lists/* \
      /tmp/*

RUN curl -L https://www.haskell.org/platform/download/$HASKELL_PLATFORM_VERSION/haskell-platform-$HASKELL_PLATFORM_VERSION-unknown-linux-x86_64.tar.gz | tar zx
RUN /usr/local/haskell/ghc-7.8.3-x86_64/bin/activate-hs

RUN cabal update && \
    cabal install -j elm elm-repl elm-get elm-reactor

RUN echo "export PATH=/root/.cabal/bin:$PATH" >> /root/.zshrc

WORKDIR /data
CMD ["tmux"]

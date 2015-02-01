FROM debian:jessie

RUN \
  apt-get update -y && \
  apt-get install -yq --no-install-recommends \
  irssi \
  irssi-scripts \
  screen \
  libnet-twitter-perl \
  libwww-shorten-perl \
  libjson-any-perl \
  libio-socket-ssl-perl && \
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

CMD TERM=screen irssi

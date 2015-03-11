FROM resin/rpi-raspbian:jessie-2015-02-18

RUN \
  apt-get update -y && \
  apt-get install -yq --no-install-recommends \
  irssi \
  irssi-scripts \
  screen \
  libwww-perl \
  libwww-curl-perl \
  libjson-perl \
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


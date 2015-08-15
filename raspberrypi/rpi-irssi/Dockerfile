FROM resin/rpi-raspbian:jessie-2015-08-12

RUN  \
  apt-get update -y && \
  apt-get install -yq \
  irssi \
  libnet-twitter-perl \
  libwww-shorten-perl \
  libjson-any-perl \
  libwww-curl-perl && \
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

# LOCALTIME
RUN rm /etc/localtime && \
    cp -p /usr/share/zoneinfo/America/Los_Angeles /etc/localtime && \
    printf America/Los_Angeles > /etc/timezone

# SUPPORT 256 COLOR
ENV TERM=xterm-256color

CMD ["irssi"]

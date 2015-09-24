FROM resin/rpi-raspbian:wheezy-2015-08-12

RUN apt-get update -y && \
    apt-get install -yq \
    libwww-curl-perl && \
    rm -rf \
      /var/lib/apt/lists/* \
      /tmp/* \
      /var/tmp/* \
      /var/cache/man/* \
      /var/cache/apt/* \
      /usr/share/doc/* \
      /usr/share/info/* \
      /usr/share/man/*

RUN echo "deb http://archive.raspbian.org/raspbian jessie main contrib non-free rpi firmware" >> /etc/apt/sources.list

RUN  \
  apt-get update -y && \
  apt-get install -yq wget \
  irssi \
  libnet-twitter-perl \
  libwww-shorten-perl \
  libjson-any-perl && \
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
ENV TERM=screen-256color

CMD ["irssi"]

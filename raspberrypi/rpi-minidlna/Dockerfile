
FROM resin/rpi-raspbian:wheezy-2015-02-08

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive \
    apt-get install -yq --no-install-recommends minidlna && \
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

RUN ln -s /var/lib/minidlna /data

CMD minidlna -d

FROM alpine

RUN apk --update add \
      ca-certificates \
      ruby \
      ncurses \
      ruby-io-console \
      ruby-json \
      ruby-dev \
    && gem install galileo \
    && apk del ruby-dev \
    && rm -rf /var/cache/apk* /tmp /usr/share/ri

ENTRYPOINT ["galileo"]

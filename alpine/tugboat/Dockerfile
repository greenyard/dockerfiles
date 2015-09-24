FROM alpine

RUN apk --update add \
      ca-certificates \
      ruby \
      ruby-dev \
    && gem install tugboat \
    && apk del ruby-dev \
    && rm -rf /var/cache/apk* /tmp /usr/share/ri

ENTRYPOINT ["tugboat"]

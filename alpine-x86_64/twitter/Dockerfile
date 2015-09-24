FROM alpine

RUN apk --update add \
      ca-certificates \
      make \
      g++ \
      ruby \
      ruby-json \
      ruby-io-console \
      ruby-dev \
    && gem install t \
    && apk del make g++ ruby-dev \
    && rm -rf /var/cache/apk* /tmp /usr/share/ri

ENTRYPOINT ["t"]

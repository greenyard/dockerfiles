FROM alpine

RUN apk --update add \
  ca-certificates \
  ruby \
  ruby-bundler \
  ruby-dev && \
  rm -rf /usr/share/ri

RUN gem install tugboat

ENTRYPOINT ["tugboat"]

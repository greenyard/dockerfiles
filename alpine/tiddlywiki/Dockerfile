FROM alpine

RUN apk --update add nodejs nodejs-dev

RUN npm install -g tiddlywiki

VOLUME /var/lib/tiddlywiki
WORKDIR /var/lib/tiddlywiki

EXPOSE 8080

CMD tiddlywiki primary --server 8080 $:/core/save/all text/plain text/html "" ""  0.0.0.0

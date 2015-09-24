FROM alpine

RUN buildDeps='\
              g++ \
              libffi-dev \
              libxml2-dev \
              libxslt-dev \
              make \
              ruby-dev \
              ruby-nokogiri \
              zlib-dev \
              ' \
    && set -x \
    && apk add --update \
      $buildDeps \
      nodejs \
      py-pygments \
      ruby \
      ruby-json \
      yaml-dev \
    && gem install \
      github-pages \
      jekyll \
      jekyll-redirect-from \
      jekyll-sitemap \
      kramdown \
      rdiscount \
      rouge \
    && apk del $buildDeps  \
    && gem clean && rm -rf /var/cache/apk* /tmp /usr/share/ri

EXPOSE 4000
WORKDIR /data
ENTRYPOINT ["jekyll"]

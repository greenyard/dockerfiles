FROM ruby:1.9.3-wheezy

RUN apt-get update \
  && apt-get install -y \
    python-pygments \
    node \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

RUN gem install \
  github-pages \
  jekyll \
  jekyll-redirect-from \
  jekyll-sitemap \
  kramdown \
  rdiscount \
  rouge

EXPOSE 4000

WORKDIR /data

ENTRYPOINT ["jekyll"]

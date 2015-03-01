FROM resin/rpi-raspbian:jessie-2015-02-18

RUN \
  apt-get update -y && \
  apt-get install -yq --no-install-recommends \
  python-pip

RUN pip install --upgrade youtube_dl

WORKDIR /data

ENTRYPOINT ["youtube-dl"]

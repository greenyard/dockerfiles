FROM resin/rpi-raspbian:jessie-2015-02-18

RUN \
  apt-get update -y && \
  apt-get install -yq --no-install-recommends \
  python-pip wget

RUN wget -O speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/devel/speedtest_cli.py
RUN chmod +x speedtest-cli

ENTRYPOINT ["./speedtest-cli"]

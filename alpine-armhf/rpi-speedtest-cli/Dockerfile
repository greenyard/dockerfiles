FROM atomi/rpi-alpine

RUN apk --update add \
      ca-certificates \
      python \
    && wget -O speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/devel/speedtest_cli.py \
    && chmod +x speedtest-cli

ENTRYPOINT ["./speedtest-cli"]

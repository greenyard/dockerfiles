FROM resin/rpi-raspbian:jessie-2015-02-18

RUN apt-get update && apt-get install -yq --no-install-recommends wget
RUN wget http://node-arm.herokuapp.com/node_latest_armhf.deb && \
    dpkg -i node_latest_armhf.deb

RUN npm -g install node-gyp


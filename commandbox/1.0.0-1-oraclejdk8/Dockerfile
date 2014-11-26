FROM atomi/wheezy-oraclejdk:8
MAINTAINER atomi <http:/twitter.com/atomi>

RUN apt-get update -y && \
		apt-get install --no-install-recommends -yq curl java-common && \
		apt-get clean && \
		rm -rf /var/lib/apt/lists/*

# Create temp file due to https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=367297
RUN curl -O http://integration.staging.ortussolutions.com/artifacts/debs/noarch/commandbox_1.0.0-1_all.deb && \
		dpkg -i commandbox_1.0.0-1_all.deb && \
		rm commandbox_1.0.0-1_all.deb && \
		box upgrade

WORKDIR /data
ENTRYPOINT ["box"]

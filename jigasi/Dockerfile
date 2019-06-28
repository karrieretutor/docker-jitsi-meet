ARG TAG=base-java-latest
FROM karrieretutor/jitsi:$TAG

RUN \
	apt-dpkg-wrap apt-get update && \
	apt-dpkg-wrap apt-get install -y jigasi && \
	apt-cleanup

COPY rootfs/ /

VOLUME /config

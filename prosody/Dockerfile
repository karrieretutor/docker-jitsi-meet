FROM jitsi/base

#either empty or one of lua-dbi-sqlite3, lua-dbi-mysql or lua-dbi-postgresql
ARG DB_DRIVER=""
RUN \
	apt-dpkg-wrap apt-get update && \
	apt-dpkg-wrap apt-get install -t stretch-backports -y prosody ${DB_DRIVER} && \
	apt-cleanup && \
	rm -rf /etc/prosody

COPY rootfs/ /

EXPOSE 5222 5269 5347 5280

VOLUME ["/config", "/prosody-plugins-custom"]

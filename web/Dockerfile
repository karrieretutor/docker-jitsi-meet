ARG TAG=base-latest
FROM karrieretutor/jitsi:$TAG

RUN \
	apt-dpkg-wrap apt-get update && \
	apt-dpkg-wrap apt-get install -y cron nginx-extras jitsi-meet-web && \
	apt-dpkg-wrap apt-get install -y -t stretch-backports certbot && \
	apt-cleanup && \
	rm -f /etc/nginx/conf.d/default.conf && \
	rm -f /usr/share/jitsi-meet/interface_config.js

COPY rootfs/ /

RUN wget -O /usr/share/jitsi-meet/images/watermark.png https://www.karrieretutor.de/startseite/wp-content/themes/karrieretutor/assets/images/logo-karriere-tutor.png 

EXPOSE 80 443

VOLUME ["/config", "/etc/letsencrypt"]

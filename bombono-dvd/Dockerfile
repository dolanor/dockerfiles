FROM debian:buster

RUN echo deb http://www.deb-multimedia.org buster main non-free >> /etc/apt/sources.list.d/multimedia.list \
&&  apt-get update -oAcquire::AllowInsecureRepositories=true \
&&  apt-get install -y --allow-unauthenticated deb-multimedia-keyring \
&&  apt-get update \
&&  apt-get install bombono-dvd -y \
&&  rm -rf /var/lib/apt/lists/*

CMD "bombono-dvd"

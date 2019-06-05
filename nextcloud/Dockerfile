FROM ubuntu:trusty

LABEL maintainer "Tanguy ⧓ Herrmann <dolanorgit@evereska.org>"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y locales

RUN dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=C.UTF-8

ENV LANG C.UTF-8

ENV LANGUAGE C:en
ENV LANG C.UTF-8
ENV LC_ALL C.UTF-8

RUN apt-get update \
&&  apt-get install software-properties-common -y \
&&  add-apt-repository -y ppa:nextcloud-devs/client \
&&  apt-get update \
# Install nextcloud v2.3.2
&&  apt-get install -y nextcloud-client

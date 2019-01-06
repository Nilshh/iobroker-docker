FROM debian:jessie

MAINTAINER Nils Radde <https://radde.net>

ENV DEBIAN_FRONTEND noninteractive

RUN echo Europe/Berlin > /etc/timezone && dpkg-reconfigure tzdata

RUN apt-get update && apt-get install -y apt-utils build-essential curl git gnupg gnupg2 gnupg1 unzip wget

#RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -

#RUN apt-get install -y build-essential libavahi-compat-libdnssd-dev libudev-dev nodejs

RUN mkdir -p /opt/iobroker/ && chmod 777 /opt/iobroker/
WORKDIR /opt/iobroker/

#RUN npm install iobroker --unsafe-perm
#RUN npm i --production --unsafe-perm
#RUN npm audit fix


ENV DEBIAN_FRONTEND teletype
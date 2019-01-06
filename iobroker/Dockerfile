FROM debian:latest

MAINTAINER Nils Radde <https://radde.net>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y build-essential python apt-utils curl avahi-daemon git libpcap-dev libavahi-compat-libdnssd-dev libfontconfig gnupg2 locales procps libudev-dev libpam0g-dev unzip sudo wget ffmpeg android-tools-adb android-tools-fastboot

RUN curl -sL https://deb.nodesource.com/setup_8.x | bash
RUN apt-get install -y nodejs

RUN sed -i -e 's/# de_DE.UTF-8 UTF-8/de_DE.UTF-8 UTF-8/' /etc/locale.gen && \dpkg-reconfigure --frontend=noninteractive locales && \update-locale LANG=de_DE.UTF-8
ENV LANG de_DE.UTF-8 

RUN cp /usr/share/zoneinfo/Europe/Berlin /etc/localtime
ENV TZ Europe/Berlin

RUN mkdir -p /opt/iobroker/ && chmod 777 /opt/iobroker/

WORKDIR /opt/iobroker/

RUN npm install iobroker --unsafe-perm && npm i --production --unsafe-perm
RUN update-rc.d iobroker.sh remove && echo $(hostname) > .install_host
RUN npm install node-gyp -g

ENV DEBIAN_FRONTEND teletype

FROM ubuntu:bionic

# set version label
ARG BUILD_DATE
ARG VERSION
LABEL build_version="Version:- ${VERSION} Build-date:- ${BUILD_DATE}"
LABEL maintainer="matthew.williams"

RUN \
 echo "**** install runtime packages ****" && \
 apt-get update && \
 apt-get install -y \
	wget \
	screen \
	default-jdk \
	nmap && \
 echo "**** Installing Minecraft Server ****" && \
 sudo useradd -m -r -d /opt/minecraft minecraft && \
 sudo mkdir /opt/minecraft/survival && \
 sudo chown -R minecraft /opt/minecraft/survival/ \

# ports and volumes
EXPOSE 25565 25565/udp
VOLUME /config /transcode

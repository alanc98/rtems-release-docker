FROM ubuntu:latest
LABEL Description="RTEMS 5 m2004 base packages - this layer will be shared by all other images"
ENV DEBIAN_FRONTEND noninteractive
ENV TERM linux

RUN apt-get update && \
    #
    # Install tools and libraries
    #
    apt-get install -y \
       apt-utils build-essential \
       vim u-boot-tools git cmake \
       bison flex texinfo bzip2 \
       xz-utils unzip python wget pax \
       lua5.3 liblua5.3-dev libexpat1-dev \
       libpython2.7-dev zlib1g-dev libtinfo-dev && \
     rm -rf /var/lib/apt/lists/* 

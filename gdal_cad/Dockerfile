FROM ubuntu:18.04
LABEL maintainer="vistawn <vistawn@gmail.com>"

ADD sources.list /etc/apt/sources.list

ADD TeighaFileConverter4.7.deb /

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update -q -y \
    && apt-get install -y software-properties-common \
    && add-apt-repository ppa:ubuntugis/ppa \
    && apt-get update -y \
    && apt-get install -y wget tzdata python3 python3-pip gdal-bin rar unrar python3-gdal \
        xvfb qtbase5-dev libxcb-xinerama0-dev  build-essential \
    && ln -fs /usr/share/zoneinfo/Asia/Shanghai /etc/localtime  \
    && dpkg-reconfigure -f noninteractive tzdata \
    && ln -s /usr/bin/python3 /usr/bin/python \
    && ln -s /usr/bin/pip3 /usr/bin/pip \
    && dpkg -i /TeighaFileConverter4.7.deb \
    && rm -r /TeighaFileConverter4.7.deb \
    && apt-get autoclean \
    && rm -rf /var/lib/apt/lists/*


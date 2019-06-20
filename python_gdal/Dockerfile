FROM ubuntu:18.04
LABEL maintainer="vistawn <vistawn@gmail.com>"

ADD sources.list /etc/apt/sources.list

# RUN echo "Acquire::http::Proxy \"http://10.12.3.135:3142\";" | tee /etc/apt/apt.conf.d/00proxy \
RUN apt-get update -q -y \
    && apt-get install -y software-properties-common \
    && add-apt-repository ppa:ubuntugis/ppa \
    && apt-get update -y \
    && apt-get install -y wget python3 python3-pip gdal-bin rar unrar python3-gdal \
    && ln -s /usr/bin/python3 /usr/bin/python \
    && ln -s /usr/bin/pip3 /usr/bin/pip \
    && apt-get autoclean \
    && rm -rf /var/lib/apt/lists/*


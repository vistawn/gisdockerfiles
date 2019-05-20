FROM ubuntu:18.04
LABEL maintainer="vistawn <vistawn@gmail.com>"

ADD sources.list /etc/apt/sources.list

RUN apt-get update -y &&\
    apt-get install -y software-properties-common &&\
    add-apt-repository ppa:ubuntugis/ppa &&\
    apt-get update -y &&\
    apt-get install -y python3 python3-pip gdal-bin python3-gdal


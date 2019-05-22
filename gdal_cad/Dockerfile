FROM python_gdal:0.1

ADD TeighaFileConverter4.7.deb /
RUN apt-get update && apt-get -y install xvfb qtbase5-dev \
    libxcb-xinerama0-dev \
    build-essential \
    && dpkg -i /TeighaFileConverter4.7.deb \
    && rm -r /TeighaFileConverter4.7.deb \
    && apt-get autoclean \
    && rm -rf /var/lib/apt/lists/*


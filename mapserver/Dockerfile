FROM ubuntu:18.04
LABEL maintainer="vistawn <vistawn@gmail.com>"

EXPOSE 80

ADD sources.list /etc/apt/sources.list

RUN echo "Acquire::http::Proxy \"http://10.12.3.135:3142\";" | tee /etc/apt/apt.conf.d/00proxy \
    && apt-get update -q -y \
    && apt-get install -y software-properties-common \
    && add-apt-repository ppa:ubuntugis/ppa \
    && apt-get update -y \
    && apt-get install -y apache2 \
                    mapserver-bin \
                    cgi-mapserver \
                    libapache2-mod-mapcache \
                    mapcache-cgi \
    && apt-get autoclean \
    && rm -rf /var/lib/apt/lists/*
RUN a2enmod cgid \
    && echo "ServerName localhost" >> /etc/apache2/apache2.conf \
    && cp /usr/lib/cgi-bin/mapserv /usr/lib/cgi-bin/mapserv.fcgi

CMD [ "apache2ctl", "-D", "FOREGROUND"]

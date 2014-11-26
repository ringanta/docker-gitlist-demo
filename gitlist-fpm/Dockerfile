FROM debian:wheezy

MAINTAINER Roy Inganta Ginting <roy.i.ginting@gdplabs.id>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
    apt-get install -y wget git

RUN echo "deb http://packages.dotdeb.org wheezy-php55 all" > \
    /etc/apt/sources.list.d/dotdeb-php5.list && \
    wget http://www.dotdeb.org/dotdeb.gpg && \
    apt-key add dotdeb.gpg && \
    apt-get update && \
    apt-get install -y \
    php5 php5-cli php5-fpm \
    php5-mysql php5-gd \
    php5-curl php5-mcrypt && \
    php5enmod mcrypt && \
    rm -fr /var/lib/apt/list/*

ADD www.conf /etc/php5/fpm/pool.d/www.conf
ADD php-fpm.conf /etc/php5/fpm/php-fpm.conf
ADD php.ini /etc/php5/fpm/php.ini

ADD gitlist-0.5.0.tar.gz /var/www/
RUN mkdir -p /var/www/repositories && \
    mkdir -p /var/www/gitlist/cache && \
    chmod 777 /var/www/gitlist/cache && \
    mkdir -p /var/log/fpm

VOLUME ["/var/www/gitlist"]

EXPOSE 9000

CMD ["usr/sbin/php5-fpm", "--nodaemonize"]

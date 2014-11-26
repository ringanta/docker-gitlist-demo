FROM debian:wheezy

MAINTAINER Roy Inganta Ginting <roy.i.ginting@gdplabs.id>

RUN apt-key adv --keyserver pgp.mit.edu --recv-keys 573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62
RUN echo "deb http://nginx.org/packages/debian/ wheezy nginx" >> /etc/apt/sources.list

ENV NGINX_VERSION 1.6.2-1~wheezy
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
    apt-get install -y \
    nginx=${NGINX_VERSION} curl && \
    rm -fr /var/lib/apt/lists/*

ADD nginx.conf /etc/nginx/nginx.conf
ADD gitlist /etc/nginx/sites-available/
RUN mkdir -p /etc/nginx/sites-enabled
RUN rm /etc/nginx/conf.d/default.conf
RUN ln -sf /etc/nginx/sites-available/gitlist /etc/nginx/sites-enabled/

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

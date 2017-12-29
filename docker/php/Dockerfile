#FROM centos:6.9
#
#COPY install.sh /
#RUN chmod +x /install.sh
#CMD bash -C '/install.sh';'bash'



FROM php:7.2-fpm

RUN apt-get update && apt-get -y install --no-install-recommends apt-utils \
        git g++ libcurl4-gnutls-dev libicu-dev libmcrypt-dev libpq-dev libxml2-dev unzip zlib1g-dev \
    && pecl install redis \
    && docker-php-ext-enable redis \
    && docker-php-ext-install intl pdo_pgsql \
    && apt-get autoremove && apt-get autoclean \
    && rm -rf /var/lib/apt/lists/*

# RUN echo 'date.timezone="Asia/Saigon"' >>  /usr/local/etc/php/conf.d/date.ini
RUN echo 'session.save_path = "/tmp"' >>  /usr/local/etc/php/conf.d/session.ini

CMD [ "php-fpm", \
        "--nodaemonize"]

FROM php:7.4-fpm

MAINTAINER AlexP007

RUN apt-get update && apt-get install -y \
 git zip unzip pkg-config libpq-dev libxml2-dev libxslt1-dev libzip-dev libpng-dev libonig-dev libfreetype6-dev libjpeg62-turbo-dev libxml2-dev \
    && docker-php-ext-install -j$(nproc) bcmath pdo_mysql mysqli gd zip exif soap mbstring pcntl sockets xsl\
    && apt-get clean && apt-get autoclean

### OCI8 install ###

# uncomment if want to use php7.4 with oci8

# RUN apt-get update && apt-get -y install wget bsdtar libaio1 && \
#    wget -qO- https://download.oracle.com/otn_software/linux/instantclient/185000/instantclient-basic-linux.x64-18.5.0.0.0dbru.zip | bsdtar -xvf- -C /usr/local && \
#    wget -qO- https://download.oracle.com/otn_software/linux/instantclient/185000/instantclient-sdk-linux.x64-18.5.0.0.0dbru.zip | bsdtar -xvf-  -C /usr/local && \
#    wget -qO- https://download.oracle.com/otn_software/linux/instantclient/185000/instantclient-sqlplus-linux.x64-18.5.0.0.0dbru.zip | bsdtar -xvf- -C /usr/local && \
#    ln -s /usr/local/instantclient_12_2 /usr/local/instantclient && \
#    ln -s /usr/local/instantclient/libclntsh.so.* /usr/local/instantclient/libclntsh.so && \
#    ln -s /usr/local/instantclient/lib* /usr/lib && \
#    ln -s /usr/local/instantclient/sqlplus /usr/bin/sqlplus

# RUN echo 'instantclient,/usr/local/instantclient/' | pecl install oci8-2.2.0 \
#    && docker-php-ext-enable oci8 \
#    && docker-php-ext-configure pdo_oci --with-pdo-oci=instantclient,/usr/local/instantclient \
#    && docker-php-ext-install pdo_oci

# configuration
ADD ./php/php.ini /usr/local/etc/php/conf.d/php_custom.ini
ADD ./php/fpm.conf /usr/local/etc/pool.d/fpm_custom.conf

RUN usermod -u 1000 www-data

WORKDIR /var/www/project

EXPOSE 9000

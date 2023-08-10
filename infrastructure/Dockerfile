ARG PHP

FROM php:${PHP}-fpm-alpine

LABEL manteiner = 'Jose Mancilla - For Laravel' \
      version = "v1.0"
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
# PHP Modules #
RUN chmod +x /usr/local/bin/install-php-extensions && sync && \
    install-php-extensions redis mysqli exif gd zip soap mcrypt imap bcmath pdo_mysql ssh2 opcache sockets intl imagick @composer
# ADDITIONAL SOFTWARE
RUN apk add -U imagemagick ghostscript tzdata curl && rm -rf /var/cache/apk/*
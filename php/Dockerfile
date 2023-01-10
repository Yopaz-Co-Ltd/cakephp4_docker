FROM node:16 as node
FROM php:8.1-fpm

RUN apt update -yqq && apt install --no-install-recommends -yqq \
    git \
    wget \
    zip \
    unzip \
    vim \
    msmtp msmtp-mta \
    libicu-dev \
    zlib1g-dev \
    gnupg \
    locales \
    fonts-ipafont \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && echo 'Asia/Tokyo' > /etc/timezone \
    && ln -sf  /usr/share/zoneinfo/Asia/Tokyo /etc/localtime \
    && docker-php-ext-install intl pdo_mysql bcmath exif

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN usermod -u 1000 www-data && chown -R www-data:www-data /var/www

# composer
COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer
# node command
COPY --from=node /usr/local/bin /usr/local/bin
# npm command
COPY --from=node /usr/local/lib /usr/local/lib

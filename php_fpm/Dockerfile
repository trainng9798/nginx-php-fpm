FROM php:7.4-fpm-buster
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        sqlite3 \
        libsqlite3-dev \
        libicu-dev \
        libxslt-dev \
        libzip-dev \
        libpq-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd
RUN docker-php-ext-install fileinfo pdo_mysql pdo_sqlite mysqli exif intl xsl json soap dom zip opcache iconv  pgsql pdo_pgsql  && \
    pecl install xdebug-2.9.2 && \
    pecl install -o -f redis && \
    echo "extension=redis.so" > /usr/local/etc/php/conf.d/redis.ini

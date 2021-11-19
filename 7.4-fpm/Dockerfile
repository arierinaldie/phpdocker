FROM php:7.4-fpm

RUN apt-get update \
    && apt-get install --no-install-recommends --no-upgrade -y nano zip unzip wget software-properties-common \
    && apt-get install --no-install-recommends --no-upgrade -y libzip-dev libpcre3-dev libicu-dev libpq-dev libmemcached-dev libonig-dev libxml2-dev libfreetype-dev libjpeg-dev libpng-dev \
    && docker-php-ext-configure pgsql --with-pgsql=/usr/local/pgsql \
    && docker-php-ext-install exif pdo pdo_mysql mysqli pdo_pgsql pgsql bcmath ctype fileinfo json mbstring tokenizer opcache \
    && docker-php-ext-install zip intl xml dom xmlrpc xmlwriter gd sockets \
    && docker-php-ext-install -j$(nproc) iconv \
    && rm -rf /tmp/*

RUN apt-get install --no-install-recommends --no-upgrade -y supervisor git openssh-client libcurl4-openssl-dev \
    && docker-php-ext-install curl \
    && rm -rf /tmp/*

RUN docker-php-source extract \
    && mkdir -p /usr/src/php/ext/igbinary \
    && curl -fsSL https://github.com/igbinary/igbinary/archive/3.2.0.tar.gz | tar xvz -C /usr/src/php/ext/igbinary --strip 1 \
    && docker-php-ext-install igbinary \
    && mkdir -p /usr/src/php/ext/redis \
    && curl -fsSL https://github.com/phpredis/phpredis/archive/5.3.0.tar.gz | tar xvz -C /usr/src/php/ext/redis --strip 1 \
    && docker-php-ext-configure redis --enable-redis-igbinary \
    && docker-php-ext-install redis \
    && mkdir -p /usr/src/php/ext/apcu \
    && curl -fsSL https://github.com/krakjoe/apcu/archive/v5.1.17.tar.gz | tar xvz -C /usr/src/php/ext/apcu --strip 1 \
    && docker-php-ext-install apcu \
    && docker-php-source delete

RUN echo 'opcache.interned_strings_buffer=16' >> /usr/local/etc/php/conf.d/docker-php-ext-opcache.ini \
    && echo 'opcache.load_comments=Off' >> /usr/local/etc/php/conf.d/docker-php-ext-opcache.ini \
    && echo 'opcache.max_accelerated_files=16000' >> /usr/local/etc/php/conf.d/docker-php-ext-opcache.ini \
    && echo 'opcache.save_comments=Off' >> /usr/local/etc/php/conf.d/docker-php-ext-opcache.ini

ENV COMPOSER_HOME /composer
ENV PATH ./vendor/bin:/composer/vendor/bin:$PATH
ENV COMPOSER_ALLOW_SUPERUSER 1
RUN curl -s https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer

COPY ./supervisord.conf /etc/supervisor
EXPOSE 9001

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/supervisord.conf"]

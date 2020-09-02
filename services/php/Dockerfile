FROM php:7.2-fpm
RUN mkdir -p /usr/src/php/ext \
    && docker-php-ext-install pdo_mysql \
    && pecl install xdebug && docker-php-ext-enable xdebug \
    && pecl install xhprof && docker-php-ext-enable xhprof \
    && pecl install protobuf && docker-php-ext-enable protobuf \
    && pecl install swoole && docker-php-ext-enable swoole \
    && curl -L -o /tmp/syx.tar.gz https://github.com/syx-cloud/Syx/archive/v0.0.6.tar.gz
    && tar xfz /tmp/syx.tar.gz && mv Syx-0.0.6 /usr/src/php/ext/syx \
    && docker-php-ext-install syx && rm -rf /tmp/syx.tar.gz \
    && curl -L -o /tmp/redis.tar.gz https://github.com/phpredis/phpredis/archive/5.3.1.tar.gz \
    && tar xfz /tmp/redis.tar.gz && mv phpredis-5.3.1 /usr/src/php/ext/redis \
    && docker-php-ext-install redis && rm -rf /tmp/redis.tar.gz \
    && rm -rf /usr/src/php/ext && rm -rf /tmp/pear
FROM registry.cn-beijing.aliyuncs.com/excellent3207/php_7.2_swoole_4.2.13:v1
COPY ./docker-entrypoint /usr/local/bin/
RUN chmod a+x /usr/local/bin/docker-entrypoint
RUN docker-php-ext-install zip
RUN docker-php-ext-install mcrypt
RUN apt-get update \
    && apt-get install -y libmcrypt-dev
RUN pecl install mcrypt-1.0.1
RUN docker-php-ext-enable mcrypt
FROM registry.cn-beijing.aliyuncs.com/excellent3207/php_swoole:v1
COPY ./docker-entrypoint /usr/local/bin/
RUN chmod a+x /usr/local/bin/docker-entrypoint
RUN docker-php-ext-install zip
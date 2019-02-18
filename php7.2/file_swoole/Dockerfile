FROM registry.cn-beijing.aliyuncs.com/excellent3207/php_7.2:v2
RUN docker-php-ext-install zip
RUN echo "deb http://mirrors.163.com/debian/ jessie main non-free contrib" > /etc/apt/sources.list \
    && echo "deb http://mirrors.163.com/debian/ jessie-updates main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb http://mirrors.163.com/debian/ jessie-backports main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.163.com/debian/ jessie main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.163.com/debian/ jessie-updates main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.163.com/debian/ jessie-backports main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb http://mirrors.163.com/debian-security/ jessie/updates main non-free contrib" >> /etc/apt/sources.list
RUN docker-php-ext-install sockets
RUN apt-get update && apt-get install -y --no-install-recommends wget \
    && wget -O /tmp/swoole.tar.gz https://github.com/swoole/swoole-src/archive/v4.2.13.tar.gz \
    && /tmp/swoole \
    && ar -xzf /tmp/swoole.tar.gz -C /tmp/swoole --strip-components=1
WORKDIR /tmp/swoole
RUN phpize && ./configure && make && make install && docker-php-ext-enable swoole
RUN rm -rf /var/lib/apt/lists/* && rm -f /tmp/swoole.tar.gz && rm -r /tmp/swoole && apt-get purge -y --auto-remove wget

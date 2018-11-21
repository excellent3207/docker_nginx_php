FROM registry.cn-beijing.aliyuncs.com/excellent3207/php_7.2:v1
RUN cat > /etc/apt/sources.list << EOF   \
    deb http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse  \
    deb http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse  \
    deb http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse  \
    deb http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse  \
    deb http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse  \
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse  \
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse  \
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse  \
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse  \
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse \
    EOF
RUN apt-get update && \
    apt-get install -y --no-install-recommends cron && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get clean
    
COPY ./docker-entrypoint /usr/local/bin/
RUN chmod a+x /usr/local/bin/docker-entrypoint
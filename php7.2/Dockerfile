FROM registry.cn-beijing.aliyuncs.com/excellent3207/php_7.2:v1
COPY ./source.list /etc/apt/
RUN apt-get update && \
    apt-get install -y --no-install-recommends cron && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get clean
    
COPY ./docker-entrypoint /usr/local/bin/
RUN chmod a+x /usr/local/bin/docker-entrypoint
FROM registry.cn-beijing.aliyuncs.com/excellent3207/php_7.2:v1
RUN apt-get update && \
    apt-get install -y cron && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get clean
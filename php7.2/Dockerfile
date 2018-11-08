FROM registry.cn-beijing.aliyuncs.com/excellent3207/php_7.2:v1
RUN apt-get update && \
    apt-get install apt-utils && \
    apt-get install -y --no-install-recommends \
    cron && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get clean

RUN chmod +x /docker-entrypoint.sh

ENV LC_ALL C.UTF-8
ENTRYPOINT ["/docker-entrypoint.sh"]
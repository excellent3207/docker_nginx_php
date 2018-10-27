下载docker环境部署文件和配置
curl -o /var/docker_nginx_php.zip http://xjp-software.oss-cn-beijing.aliyuncs.com/docker_nginx_php.zip \
&& unzip -n -d /var/www /var/docker_nginx_php.zip

本地环境，如果是parallel，执行下面命令，讲项目源文件做一个软连接
ln -s /media/psf/gitsource /var/docker_nginx_php/web

登录阿里云
docker login --username=xingjinpeng3207 registry.cn-beijing.aliyuncs.com

下载镜像
docker pull registry.cn-beijing.aliyuncs.com/excellent3207/redis5:v1
docker pull registry.cn-beijing.aliyuncs.com/excellent3207/nginx_1.15.5:v1
docker pull registry.cn-beijing.aliyuncs.com/excellent3207/php_7.2:v1

此目录下文件介绍：
php7.2 下面包括php配置文件，和docker php配置文件同步
nginx1.15.5 包括conf1..配置文件
redis5 包括data数据文件，和conf配置文件

在此目录下，执行:
docker-compose -f docker-compose.yml up
批量创建容器
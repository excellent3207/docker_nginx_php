现在此目录：git clone -b syh_env https://github.com/excellent3207/docker_nginx_php.git /var/www/syh_env

登录阿里云
docker login --username=xingjinpeng3207 registry.cn-beijing.aliyuncs.com

下载镜像
docker pull registry.cn-beijing.aliyuncs.com/excellent3207/redis5:v1
docker pull registry.cn-beijing.aliyuncs.com/excellent3207/nginx_1.15.5:v1
docker pull registry.cn-beijing.aliyuncs.com/excellent3207/php_7.2:v1

在docker-compose.yml中：
修改项目源码路径值本地路径

注意：要修改nginx的fastcgi的主机名为php的host以及项目源码路径

在此目录下，执行:
docker-compose -f docker-compose.yml up -d
或本地paralle环境，需要修改项目目录：
docker-compose -f docker-compose-local.yml up -d
批量创建容器

此目录下文件介绍：
php7.2 下面包括php配置文件，和docker php配置文件同步
nginx1.15.5 包括conf1..配置文件
redis5 包括data数据文件，和conf配置文件
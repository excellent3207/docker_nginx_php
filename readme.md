一、现在此目录：git clone -b fr_jieba https://github.com/excellent3207/docker_nginx_php.git /var/www/fr_jieba
dfdfd

二、登录阿里云
docker login --username=xingjinpeng3207 registry.cn-beijing.aliyuncs.com

三、下载镜像
docker pull registry.cn-beijing.aliyuncs.com/excellent3207/redis5:v1
docker pull registry.cn-beijing.aliyuncs.com/excellent3207/nginx_1.15.5:v2
docker pull registry.cn-beijing.aliyuncs.com/excellent3207/php_7.2_swoole_4.2.13:v1

四、在docker-compose.yml中：
修改项目源码路径值本地路径

五、注意：要修改nginx的fastcgi的主机名为php的host以及项目源码路径

六、在此目录下，执行:
docker-compose -f docker-compose.yml up -d
或本地paralle环境，需要修改项目目录：
docker-compose -f docker-compose-local.yml up -d
批量创建容器

此目录下文件介绍：
php7.2 下面包括php配置文件，和docker php配置文件同步
nginx1.15.5 包括conf1..配置文件
redis5 包括data数据文件，和conf配置文件

七、下载项目到/var/www/syh_env/web下：
git clone -b master http://120.27.188.111/root/jieba.git /var/www/fr_jieba

八、更改执行权限
mkdir /var/www/syh_env/web/syh_server1_6_0/runtime
mkdir /var/www/syh_env/web/syh_server1_6_0/public/wx_h5/qrcode
docker exec server容器ID chown -R www-data:www-data /opt/web/syh_server1_6_0/runtime
docker exec server容器ID chown -R www-data:www-data /opt/web/syh_server1_6_0/public/wx_h5/qrcode
docker exec service容器ID chown -R www-data:www-data /opt/web/syh_service1_6_0/runtime

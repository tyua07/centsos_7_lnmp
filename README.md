# Docker LNMP环境 Dockerfile


![](https://raw.githubusercontent.com/docker/docker/master/docs/static_files/docker-logo-compressed.png "Docker")

## 安装

1 clone 到本地 
```
git clone https://github.com/tyua07/centsos_7_lnmp.git
``` 

2 执行docker build
```
docker build -t="yangyifan/centos_7_lnmp:v1" .
```


## 启动

* 运行镜像
 ```docker run -d -it -p 80 cb2f9b937632 /bin/bash```  ，其中"cb2f9b937632"为镜像的 IMAGE ID。

* 启动nginx 
```
/usr/local/nginx-1.9.9/sbin/nginx 
```

* 启动php ```/usr/local/php5.6/sbin/php-fpm``` 

* 初始化mysql

```
mkdir -p /var/log/mariadb/ && chown -R mysql:mysql /var/log/mariadb/ && /usr/local/mysql/scripts/mysql_install_db --basedir=/usr/local/mysql/ --datadir=/usr/local/www/data/mysql/data --defaults-extra-file=/etc/my.cnf --user=mysql --pid-file=/usr/local/www/data/mysql/data/mysql.pid 
```

* 启动mysql
```
/usr/local/mysql/support-files/mysql.server start
```

* 启动redis
```
/usr/local/redis-3.0.6/bin/redis-server /usr/local/redis-3.0.6/redis.conf
```

## 注意


* 依赖Centos7系统，如果Docker Hub pull很慢，建议去Daocloud.io去下载。
* 编译时间可能会很长，因为没有yum去安装。
* ```soft``` 文件夹为源码包，如果需要其他版本可以去下载。

## 源码网站


* Nginx ```wget http://nginx.org/download/nginx-1.9.9.tar.gz  #下载地址 http://nginx.org/en/download.html```
* Mysql ```wget http://dev.mysql.com/get/Downloads/MySQL-5.6/mysql-5.6.28.tar.gz # 下载地址 http://dev.mysql.com/downloads/mysql/```
* PHP ```wget http://cn2.php.net/distributions/php-5.6.16.tar.gz # 下载地址 http://php.net/get/php-5.6.16.tar.gz/from/a/mirror```
* Libmcrypt ```wget ftp://mcrypt.hellug.gr/pub/crypto/mcrypt/libmcrypt/libmcrypt-2.5.7.tar.gz # 下载地址 http://mcrypt.hellug.gr/lib/```
* Reids ```wget http://download.redis.io/releases/redis-3.0.6.tar.gz # 下载地址 http://redis.io/```



## License


MIT 

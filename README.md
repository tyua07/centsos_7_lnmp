### 启动

* 启动nginx /usr/local/nginx-1.9.9/sbin/nginx 

* 启动php /usr/local/php5.6/sbin/php-fpm 

* 初始化mysql mkdir -p /var/log/mariadb/ && chown -R mysql:mysql /var/log/mariadb/ && /usr/local/mysql/scripts/mysql_install_db --basedir=/usr/local/mysql/ --datadir=/usr/local/www/data/mysql/data --defaults-extra-file=/etc/my.cnf --user=mysql --pid-file=/usr/local/www/data/mysql/data/mysql.pid 

* 启动mysql /usr/local/mysql/support-files/mysql.server start

* 启动redis /usr/local/redis-3.0.6/bin/redis-server /usr/local/redis-3.0.6/redis.conf
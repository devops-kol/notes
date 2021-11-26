
## ********* NGINX *********


**1. Установка NGINX с помощью пакетного менеджера**
```
sudo apt install nginx
```

**2. Установка NGINX из исходного кода**

> Устанавливаем инструменты компиляции
`sudo apt install build-essential`  

> Скачиваем исходный код nginx
`wget https://nginx.org/download/nginx-1.21.0.tar.gz`

> Устанавливаем дополнительные пакеты для запуска модулей nginx
```
sudo apt install -y libpcre3 \
libpcre3-dev \
zlib1g \
zlib1g-dev \
libssl-dev \
libgd-dev \
libxml2 \
libxml2-dev \
uuid-dev
```

> Сборка NGINX с префиксами
```
./configure \
--sbin-path=/usr/bin/nginx \
--conf-path=/etc/nginx/nginx.conf \
--pid-path=/var/run/nginx.pid \
--error-log-path=/var/log/nginx/error.log \
--http-log-path=/var/log/nginx/access.log \
--with-debug \
--with-pcre \
--with-http_ssl_module \
&& make \
&& make install
```

**3. Установка NGINX в качестве сервиса**

> Создаем файл сервиса NGINX
`vim /lib/systemd/system/nginx.service`

> Вставляем содержимое
```
[Unit]
Description=The NGINX HTTP and reverse proxy server
After=syslog.target network-online.target remote-fs.target nss-lookup.target
Wants=network-online.target

[Service]
Type=forking
PIDFile=/run/nginx.pid
ExecStartPre=/usr/bin/nginx -t
ExecStart=/usr/bin/nginx
ExecReload=/usr/bin/nginx -s reload
ExecStop=/bin/kill -s QUIT $MAINPID
PrivateTmp=true

[Install]
WantedBy=multi-user.target
```

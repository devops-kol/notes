#########################
********* NGINX *********
#########################

1. Установка NGINX с помощью пакетного менеджера
```
sudo apt install nginx
```

2. Установка NGINX из исходного кода

<!-- Устанавливаем инструменты компиляции -->
`sudo apt install build-essential`  

<!-- Скачиваем исходный код nginx -->                          
`wget https://nginx.org/download/nginx-1.21.0.tar.gz`

<!-- Устанавливаем дополнительные пакеты для запуска модулей nginx -->
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

<!-- Сборка NGINX с префиксами -->
```
./configure --sbin-path=/usr/bin/nginx \
--conf-path=/etc/nginx/nginx.conf \
--error-log-path=/var/log/nginx/error.log \
--http-log-path=/var/log/nginx/access.log \
--with-debug \
--with-pcre \
--with-http_ssl_module \
&& make \
&& make install
```

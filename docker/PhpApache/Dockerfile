#FROM php:8.0-apache
#php8のdockerイメージだとssl.confの設定が何故か通らない。原因不明。
FROM php:7.4-apache

# このイメージではapt-getでmysql_pdoを入れられないとのこと。
# dockerhub参照) https://hub.docker.com/_/php/

# Laravelのサーバ要件を満たす様にphpの拡張をインストールする
# ※ 下記は最低限必要なサーバ要件の為、案件毎に必要な拡張機能が必要であれば適宜追加する
# Laravel公式参照) https://readouble.com/laravel/8.x/ja/deployment.html#server-requirements

# 抜粋)
#-------------------
#Laravelフレームワークにはいくつかのシステム要件があります。Webサーバへ確実に以下のPHP最低バージョンと拡張機能を用意してください。
#PHP7.3以上
#BCMath PHP 拡張
#Ctype PHP 拡張
#Fileinfo PHP 拡張
#JSON PHP 拡張
#Mbstring PHP 拡張
#OpenSSL PHP 拡張
#PDO PHP 拡張
#Tokenizer PHP 拡張
#XML PHP 拡張
#-------------------

COPY config/ssl.conf /etc/apache2/sites-available/
COPY config/key/ssl.key /root/
COPY config/key/ssl.crt /root/

RUN \
  docker-php-ext-install \
    pdo_mysql \ 
  && rm /etc/apache2/sites-available/default-ssl.conf \
  && a2enmod ssl \
  && a2ensite ssl
#以下イメージに既に入っているっぽい
#    bcmath \
#    ctype \
#    fileinfo \
#    json \
#    mbstring \
#    pdo \
#    tokenizer \
#    xml



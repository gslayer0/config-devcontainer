FROM php:8.2.20-fpm-alpine3.20

# Install PHP extensions with mlocati PHP extension install helper
ADD --chmod=0755 https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN install-php-extensions imagick sqlsrv pdo_sqlsrv mysqli pdo_mysql redis bcmath gd exif pcntl intl zip

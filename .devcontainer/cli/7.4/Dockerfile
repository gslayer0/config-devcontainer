# From official php image.
FROM php:7.4-cli-alpine

# Create a user group and account under id 1000.
RUN addgroup -g 1000 -S puppet && adduser -u 1000 -D puppet -G puppet

# Install quality-of-life packages.
RUN apk add --update --no-cache bash curl git vim less openssh

# Install PHP extensions with mlocati PHP extension install helper
ADD --chmod=0755 https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN install-php-extensions imagick sqlsrv pdo_sqlsrv mysqli pdo_mysql redis bcmath gd exif pcntl intl zip

# Install composer for php dependencies.
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/bin/composer

# Add color to bash terminal
ENV TERM xterm-256color

# Prevent container from exiting early.
CMD ["sleep", "infinity"]

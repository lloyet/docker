FROM php:7.0-apache

COPY hooky/ /var/www/html/

RUN docker-php-ext-install bcmath && \
		apt-get update && apt-get install --no-install-recommends git -y && apt-get clean && \
		php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
		php composer-setup.php && \
		php -r "unlink('composer-setup.php');" && \
		./composer.phar install

FROM php:7-cli

RUN apt-get -y update && apt-get -y install \
	libzip-dev \
	zip \
	unzip

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug \
	&& docker-php-ext-install \
		pdo_mysql \
		zip

WORKDIR /project

COPY --from=composer:1.10.15 /usr/bin/composer /usr/bin/composer

EXPOSE 80/tcp

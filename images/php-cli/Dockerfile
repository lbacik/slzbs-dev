FROM php:7-cli

RUN apt-get -y update && apt-get -y install \
	libzip-dev

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug \
	&& docker-php-ext-install \
		pdo_mysql \
		zip

WORKDIR /project

COPY --from=composer /usr/bin/composer /usr/bin/composer

EXPOSE 80/tcp

# Dockerfile
FROM docker.io/library/php:8.1-cli

RUN apt-get update && apt-get install -y libmcrypt-dev && apt-get install -y libonig-dev

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN docker-php-ext-install pdo pdo_mysql mbstring

WORKDIR /app
COPY . /app

RUN composer install

EXPOSE 8000
CMD php artisan serve --host=0.0.0.0 --port=8000

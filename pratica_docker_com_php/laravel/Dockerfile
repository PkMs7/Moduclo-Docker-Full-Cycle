FROM php:7.4-cli

WORKDIR /var/www

RUN apt-get update && \
    apt-get install libzip-dev -y && \
    docker-php-ext-install zip

# https://getcomposer.org/download/

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php -r "if (hash_file('sha384', 'composer-setup.php') === 'dac665fdc30fdd8ec78b38b9800061b4150413ff2e3b6f88543c636f7cd84f6db9189d43a81e5503cda447da73c7e5b6') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');"

# https://laravel.com/docs/11.x/installation

RUN php composer.phar create-project laravel/laravel fc-docker-laravel-patrick-app

ENTRYPOINT [ "php","fc-docker-laravel-patrick-app/artisan","serve" ]
CMD [ "--host=0.0.0.0" ]
FROM wordpress:6.6.2-php8.1

LABEL authors="Vitalii Bryl"

ARG APP_PATH=/var/www/html

RUN apt-get update && apt-get install -y less

RUN docker-php-ext-install pdo_mysql

COPY php.ini /usr/local/etc/php/conf.d/custom-php.ini

RUN pecl install xdebug-3.1.6

## Composer
RUN curl -sLS https://getcomposer.org/installer | \
    php -- \
      --install-dir=/usr/bin/ \
      --filename=composer

## WP-Cli
ENV WP_CLI_ALLOW_ROOT=true

RUN curl -sS https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar \
      -o /usr/bin/wp && \
    chmod +x /usr/bin/wp && \
    wp --info

WORKDIR $APP_PATH

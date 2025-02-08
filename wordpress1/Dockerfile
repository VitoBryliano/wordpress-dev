FROM wordpress:6.6.2-php8.1

LABEL authors="Vitalii Bryl"

ARG APP_PATH=/var/www/html

RUN docker-php-ext-install pdo_mysql

COPY php.ini /usr/local/etc/php/conf.d/custom-php.ini

RUN pecl install xdebug

RUN curl -sLS https://getcomposer.org/installer | \
    php -- \
      --install-dir=/usr/bin/ \
      --filename=composer && \
    curl -sS https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar \
      -o /usr/bin/wp && \
    chmod +x /usr/bin/wp

WORKDIR $APP_PATH

#RUN composer require --dev \
#    squizlabs/php_codesniffer \
#    friendsofphp/php-cs-fixer \
#    wp-coding-standards/wpcs \

#RUN composer config allow-plugins.dealerdirect/phpcodesniffer-composer-installer true


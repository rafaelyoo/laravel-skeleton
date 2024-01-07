FROM php:8.2-fpm

RUN apt update -y \
&& apt -y install tzdata \
libicu-dev \
libonig-dev \
libpq-dev \
git
 
RUN docker-php-ext-configure intl && docker-php-ext-install intl

RUN docker-php-ext-configure pcntl && docker-php-ext-install pcntl

RUN docker-php-ext-configure pdo_pgsql && docker-php-ext-install pdo_pgsql

RUN docker-php-ext-configure mbstring && docker-php-ext-install mbstring
  
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer
 
CMD ["php-fpm"]
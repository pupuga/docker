FROM nginx:latest

RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections

RUN apt-get update -y
RUN apt-get install -y apt-utils

# Install important libraries
RUN apt-get -y install git curl libcurl3-dev libxml2-dev zip openssl libpng-dev libsqlite3-dev cron mc 
                                                         
# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Other PHP Extensions
RUN docker-php-ext-install bcmath 
RUN docker-php-ext-install calendar  
RUN docker-php-ext-install dba 
RUN docker-php-ext-install exif  
RUN docker-php-ext-install gd 
RUN docker-php-ext-install gettext 
RUN docker-php-ext-install mysqli 
RUN docker-php-ext-install opcache  
RUN docker-php-ext-install pdo_mysql 
RUN docker-php-ext-install shmop  
RUN docker-php-ext-install sockets 
RUN docker-php-ext-install sysvmsg 
RUN docker-php-ext-install sysvsem 
RUN docker-php-ext-install sysvshm  
RUN docker-php-ext-install zend_test

# Install xdebug
RUN apt-get update && pecl install xdebug
RUN docker-php-ext-enable xdebug
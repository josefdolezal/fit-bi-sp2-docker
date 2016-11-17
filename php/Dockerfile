FROM php:7.0-apache

# PHP Extensions
RUN apt-get update
RUN apt-get install -y php5-mysql \
		sed \
		libmcrypt-dev \
		zlib1g-dev \
		libxml2-dev \
		zip

RUN docker-php-ext-install mysqli pdo pdo_mysql mcrypt zip xml

# Setup extensions
RUN cp /usr/share/php5/php.ini-production /usr/local/etc/php/php.ini
RUN sed 's,;extension=mysqli.so,extension=mysqli.so,'

# Apache mod_rewrite
RUN a2enmod rewrite

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Node
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get install -y nodejs git

# XDebug
RUN pecl install xdebug

RUN echo "zend_extension="`find /usr/local/lib/php/extensions/ -iname 'xdebug.so'` > /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_enable=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
		&& echo "xdebug.remote_autostart=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
		&& echo "xdebug.remote_connect_back=off" >> /usr/local/etc/php/conf.d/xdebug.ini \
		&& echo "xdebug.remote_handler=dbgp" >> /usr/local/etc/php/conf.d/xdebug.ini \
		&& echo "xdebug.profiler_enable=0" >> /usr/local/etc/php/conf.d/xdebug.ini \
		&& echo "xdebug.profiler_output_dir=\"/var/www/html\"" >> /usr/local/etc/php/conf.d/xdebug.ini \
		&& echo "xdebug.remote_port=9000" >> /usr/local/etc/php/conf.d/xdebug.ini \
		&& echo "xdebug.remote_connect_back=1" >> /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.idekey=\"phpstorm-xdebug\"" >> /usr/local/etc/php/conf.d/xdebug.ini

# Bower
RUN npm install -g bower

FROM phpdockerio/php73-fpm:latest
WORKDIR "/application"

# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive

# Change log permissions
RUN chmod -R 777 /application/storage/

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get install libpng-dev -y --no-install-recommends
    && apt-get -y --no-install-recommends install  php-memcached php7.3-mysql php-xdebug php-yaml \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*
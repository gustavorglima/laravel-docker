FROM dockette/php:7.1-fpm

WORKDIR '/var/app'

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys E1DD270288B4E6030699E45FA1715D88E1DF1F24 \
    && echo 'deb http://ppa.launchpad.net/git-core/ppa/ubuntu trusty main' > /etc/apt/sources.list.d/git.list \
    && apt-get update \
    && apt-get --assume-yes install git zip unzip

RUN sed -i '/^date.timezone/c date.timezone=America/Sao_Paulo' /etc/php/7.1/cli/conf.d/999-custom.ini
RUN sed -i '/^date.timezone/c date.timezone=America/Sao_Paulo' /etc/php/7.1/fpm/conf.d/999-custom.ini
RUN sed -i '/^php_admin_value\[open_basedir\]/c php_admin_value[open_basedir]=' /etc/php/7.1/fpm/php-fpm.conf
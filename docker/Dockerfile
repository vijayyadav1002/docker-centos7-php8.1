FROM centos:7.9.2009

# Update packages and install necessary tools
RUN yum -y update && \
    yum -y install epel-release yum-utils && \
    yum-config-manager --disable 'remi*' && \
    yum-config-manager --enable remi-php81

# Install Apache and PHP
RUN yum -y install httpd php php-{cli,fpm,mysqlnd,zip,devel,gd,mbstring,curl,xml,pear,bcmath,json,opcache,redis,memcache}

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Clean up unnecessary packages and files
RUN yum clean all && rm -rf /var/cache/yum
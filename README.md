# nginx-php-fpm
simple docker-compose for using nginx alongside with php-fpm

Project contains a Dockerfile that builds php-fpm:7.4 in debian buster(alpine is buggy with some extensions)
currently it will build these extensions with php:
fileinfo pdo_mysql pdo_sqlite mysqli exif intl xsl json soap dom zip opcache iconv  pgsql pdo_pgsql gd redis xdebug

if you are willing to add some extension or remove some, you just need to edit php_fpm/Dockerfile in the project.


and additionaly you might need to edit default.conf and make nginx meet your requirements.
Remember the src folder that contains your CODE needs to have a shared volumes in both nginx and php-fpm container.
This project will work with laravel project as well.(check try_files line in defaul.conf file)

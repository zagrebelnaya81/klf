FROM webdevops/php-apache:7.4

MAINTAINER Vladimir Matiash "vm@piogroup.net"

RUN apt-get update && apt-get install -y mc default-mysql-client

RUN wget -O phpunit https://phar.phpunit.de/phpunit-9.phar && chmod +x phpunit && mv phpunit /usr/local/bin/phpunit
RUN wget -O phpcs https://squizlabs.github.io/PHP_CodeSniffer/phpcs.phar && chmod +x phpcs && mv phpcs /usr/local/bin/phpcs

RUN apt-get update && apt-get install -y mc
RUN apt-get install -y xvfb libfontconfig wkhtmltopdf

RUN chmod -R 0777 /tmp/
WORKDIR /tmp/
COPY ./run_script /tmp/

RUN chmod +x run_script
CMD /tmp/run_script

WORKDIR /var/www/html
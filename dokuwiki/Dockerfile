FROM php:7.4-apache


RUN apt-get update && apt-get install -y wget systemd

RUN wget -O /usr/src/dokuwiki.tgz \
  https://download.dokuwiki.org/src/dokuwiki/dokuwiki-stable.tgz 

RUN cd /usr/src && tar xavf dokuwiki.tgz  && rm -f dokuwiki.tgz && mv dokuwiki-2020-07-29 dokuwiki

RUN mv /usr/src/dokuwiki /var/www/dokuwiki

RUN cd /var/www/ && chown -R www-data:www-data dokuwiki/

RUN cd /etc/apache2/sites-available \
 && sed -e 's,/var/www/html,/var/www/dokuwiki,' \
      < 000-default.conf \
      > 000-default.conf.tmp \
 && mv 000-default.conf.tmp 000-default.conf \
 && a2ensite 000-default

CMD apache2ctl -D FOREGROUND

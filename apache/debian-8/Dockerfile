FROM ciwe/base:debian-8
MAINTAINER lukasz@burylo.com

RUN apt-get install -y apache2

RUN sed -ri ' \
    s!^(\s*CustomLog)\s+\S+!\1 /proc/self/fd/1!g; \
    s!^(\s*ErrorLog)\s+\S+!\1 /proc/self/fd/2!g; \
    ' /etc/apache2/apache2.conf

EXPOSE 80

CMD ["apache2 -D foreground"]

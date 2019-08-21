FROM debian:jessie
MAINTAINER fgaujard <fgaujard@localhost>
RUN apt-get update && apt-get install -y apache2 subversion php5 php5-mysql libapache2-mod-php5
RUN a2enmod php5
RUN rm /var/www/html/* -f
RUN svn checkout http://subversion.developpez.com/projets/mkframework /var/www/html/
RUN chmod 777 -R /var/www/html/data/genere
CMD /usr/sbin/apache2ctl -D FOREGROUND

EXPOSE 80

#docker build -t my-apache2 ./

#docker run -dit --name my-running-app -p 80:80 my-apache2
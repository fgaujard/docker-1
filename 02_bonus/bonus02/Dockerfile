FROM debian:8

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install git apache2 iptables -y

EXPOSE 55555

RUN cd /var/www/html/
RUN git clone https://github.com/fgaujard/WebSiteForDocker.git
#RUN mv WebSiteForDocker/000-default.conf /etc/apache2/sites-available/.
RUN mv WebSiteForDocker/* .
RUN echo '<VirtualHost *:80>\n   ServerAdmin webmaster@localhost\n   DocumentRoot /var/www/html\n   Redirect "/" "http://127.0.0.1/"\n   ErrorLog ${APACHE_LOG_DIR}/error.log\n   CustomLog ${APACHE_LOG_DIR}/access.log combined\n</VirtualHost>' > /etc/apache2/sites-available/000-default.conf

CMD ["apache2ctl", "-D", "FOREGROUND"]
#docker build -t name:apache ./
#docker run -it --name Apache -p 55555:80 -d  idofbuild
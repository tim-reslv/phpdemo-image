FROM centos/php-72-centos7:7.2

# Install Apache
#RUN yum -y update
#RUN yum -y install httpd httpd-tools

# Install EPEL Repo
#RUN rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm \
# && rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm

# Install PHP
#RUN yum -y install php72w php72w-bcmath php72w-cli php72w-common php72w-intl php72w-mbstring

# Update Apache Configuration
RUN sed -E -i -e '/<Directory "\/var\/www\/html">/,/<\/Directory>/s/AllowOverride None/AllowOverride All/' /etc/httpd/conf/httpd.conf
RUN sed -E -i -e 's/DirectoryIndex (.*)$/DirectoryIndex index.php \1/g' /etc/httpd/conf/httpd.conf

EXPOSE 80

COPY index.php /var/www/html

# Start Apache
#CMD ["/usr/sbin/httpd","-D","FOREGROUND"]

#ADD entrypoint.sh /entrypoint.sh
#RUN chmod +x /entrypoint.sh
#ENTRYPOINT ["/entrypoint.sh"]

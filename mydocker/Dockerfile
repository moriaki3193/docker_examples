FROM centos:centos6
MAINTAINER Moriaki Saigusa <moriaki3193@gmail.com>

RUN yum install -y httpd
EXPOSE 80
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
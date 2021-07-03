FROM centos:7
COPY etc /etc

RUN rm -f /etc/localtime && ln -s /usr/share/zoneinfo/Europe/Moscow /etc/localtime
RUN yum update -y
RUN yum install -y isc-bind
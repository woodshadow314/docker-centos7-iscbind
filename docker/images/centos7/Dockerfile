FROM centos:7.9.2009

COPY etc/yum.repos.d /etc/yum.repos.d
RUN rm -f /etc/localtime && ln -s /usr/share/zoneinfo/Europe/Moscow /etc/localtime

RUN yum update -y
RUN yum install -y isc-bind

RUN yum install -y mc

#COPY --chown=user:group
COPY --chown=root:named etc/opt /etc/opt
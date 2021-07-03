FROM centos:7.9.2009

COPY etc/yum.repos.d /etc/yum.repos.d
RUN rm -f /etc/localtime && ln -s /usr/share/zoneinfo/Europe/Moscow /etc/localtime

RUN yum update -y
RUN yum install -y isc-bind

RUN yum install -y mc
#RUN yum autoremove 
RUN yum clean all

RUN mv /etc/opt/isc/isc-bind/named.conf /etc/opt/isc/isc-bind/named.conf_old
COPY --chown=root:named etc/opt /etc/opt
COPY --chown=root:named var /var

CMD ["/opt/isc/isc-bind/root/usr/sbin/named", "-g", "-c", "/etc/opt/isc/isc-bind/named.conf", "-u", "named"]
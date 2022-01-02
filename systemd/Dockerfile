FROM centos/systemd

MAINTAINER "Michael Buluma" <ops@buluma.me.ke>

RUN yum -y install httpd; yum clean all; systemctl enable httpd.service

EXPOSE 80

CMD ["/usr/sbin/init"]

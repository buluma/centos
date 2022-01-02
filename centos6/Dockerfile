FROM centos:6
LABEL maintainer="Michael Buluma"

#R
RUN yum clean all && yum distro-sync

#  Clean up
RUN yum -y install wget && mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.bak && wget -O /etc/yum.repos.d/CentOS-Base.repo https://www.host-stage.net/hsmirrors/centos6repofix && yum clean all

# Install Ansible and other requirements.
RUN yum makecache fast \
 && yum -y install epel-release \
 && yum -y update \
 && yum clean all

# Disable requiretty.
# RUN sed -i -e 's/^\(Defaults\s*requiretty\)/#--- \1/'  /etc/sudoers

# Install Ansible inventory file.
# RUN mkdir -p /etc/ansible
# RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

# CMD ["/sbin/init"]

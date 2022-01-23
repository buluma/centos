ROM centos:6.10
LABEL maintainer="Michael Buluma"

# Copy CentOS base
COPY CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo

# Set epel from archive
RUN rpm -ivh https://archives.fedoraproject.org/pub/archive/epel/6/x86_64/epel-release-6-8.noarch.rpm

# Install Ansible and other requirements.
RUN yum makecache fast \
# && yum -y install epel-release \ ###no longer supported
 && yum -y update \
 && yum -y install \
      ansible \
      sudo \
      which \
      initscripts \
      python-urllib3 \
      pyOpenSSL \
      python2-ndg_httpsclient \
      python-pyasn1 \
 && yum clean all

# Disable requiretty.
RUN sed -i -e 's/^\(Defaults\s*requiretty\)/#--- \1/'  /etc/sudoers

# Install Ansible inventory file.
RUN mkdir -p /etc/ansible
RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

CMD ["/sbin/init"]

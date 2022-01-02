FROM centos:6
LABEL maintainer="Michael Buluma"

# Install Ansible and other requirements.
RUN yum makecache fast \
 && yum -y install deltarpm epel-release \
 && yum -y update \
 && yum -y install \
      ansible \
      sudo \
      which \
      initscripts \
 && yum clean all

# Disable requiretty.
# RUN sed -i -e 's/^\(Defaults\s*requiretty\)/#--- \1/'  /etc/sudoers

# Install Ansible inventory file.
# RUN mkdir -p /etc/ansible
# RUN echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

# CMD ["/sbin/init"]

FROM alpine:3.21
LABEL maintainer="Tinashe Chikomo <tinashe@chikomo.net>"

# Install Ansible
RUN apk add --no-cache git sudo openssh unzip tar rsync \
  libc6-compat gcc musl-dev python3-dev libffi-dev \
  py3-pip

# Upgrade pip and Install modules
RUN pip3 install --break-system-packages pymysql yamllint ansible ansible-lint

# Add ansible config
RUN mkdir -p /etc/ansible
ADD https://raw.githubusercontent.com/hybridadmin/misc-scripts/master/linux/ansible/hosts /etc/ansible/hosts
ADD https://raw.githubusercontent.com/hybridadmin/misc-scripts/master/linux/ansible/ansible.cfg etc/ansible/ansible.cfg

VOLUME ["/sys/fs/cgroup"]

ENTRYPOINT ["/sbin/init"]

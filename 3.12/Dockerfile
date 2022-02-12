FROM alpine:3.12
LABEL maintainer="Tinashe Chikomo <tinashe@chikomo.net>"

# Install Ansible
RUN apk add --no-cache git ansible sudo openssh unzip tar rsync libc6-compat gcc musl-dev python3-dev

# Upgrade pip and Install modules
RUN python3 -m ensurepip \
    && python3 -m pip install -U pip \
    && python3 -m pip install pymysql yamllint ansible-lint

# Add ansible config
RUN mkdir -p /etc/ansible
ADD https://raw.githubusercontent.com/hybridadmin/misc-scripts/master/linux/ansible/hosts /etc/ansible/hosts
ADD https://raw.githubusercontent.com/hybridadmin/misc-scripts/master/linux/ansible/ansible.cfg etc/ansible/ansible.cfg

VOLUME ["/sys/fs/cgroup"]

ENTRYPOINT ["/sbin/init"]

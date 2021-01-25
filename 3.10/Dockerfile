FROM alpine:3.10
LABEL maintainer="Tinashe Chikomo <tinashe@chikomo.net>"

# Install Ansible
RUN apk add --no-cache git ansible sudo openssh unzip tar rsync libc6-compat

VOLUME ["/sys/fs/cgroup"]

ENTRYPOINT ["/sbin/init"]

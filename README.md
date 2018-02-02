# Ansible-SS
shadowsocks-libev service installation on VPS

## Ubuntu 16.04 
initialization
```bash
dpkg --configure -a
apt update
apt upgrade -y 
add-apt-repository ppa:ansible/ansible
apt-get update
apt install ansible git -y
```

example:
```bash
ansible-pull -C master -d /var/ansible/gitrepo -i /var/ansible/gitrepo/hosts -U https://github.com/Will-Yin/Ansible-SS.git -e "role=ubuntu1604-ss"

ansible-pull -C master -d /var/ansible/gitrepo -i /var/ansible/gitrepo/hosts \
-U https://github.com/Will-Yin/Ansible-SS.git \
-e "kernel_url=http://kernel.ubuntu.com/~kernel-ppa/mainline/v4.14.15/linux-image-4.14.15-041415-generic_4.14.15-041415.201801231530_amd64.deb" \
-e "role=ubuntu1604-ss" \
-e "ss_password=helloword" \
-e "ss_port=1080" \
-e "ss_method=rc4-md5"
```

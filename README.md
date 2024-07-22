### debian_cheat_sheet

#### apt upgrade + curl/tcpdump
```bash
apt -y update && apt -y upgrade && apt -y full-upgrade && apt -y dist-upgrade && apt -y install curl tcpdump
```



#### enable swap
```bash
free -h # check if swap file exists!
```
```bash
fallocate -l 4G /swapfile && \
chmod 600 /swapfile && \
mkswap /swapfile && \
swapon /swapfile && \
sysctl vm.swappiness=80 && \
echo '/swapfile none swap sw 0 0' | tee -a /etc/fstab
```

#### disable swap
```bash
swapoff -a # comment swapfile lines in /etc/fstab
```

#### install nerdctl
```bash
curl -L -o nerdctl.tar.gz https://github.com/containerd/nerdctl/releases/download/v2.0.0-rc.0/nerdctl-full-2.0.0-rc.0-linux-amd64.tar.gz && \
tar Cxzvvf /usr/local nerdctl.tar.gz && \
systemctl enable --now containerd && \
apt -y install iptables
```

#### Copy Win11 SSH key to the Debian server
```bash
type $env:USERPROFILE\.ssh\id_rsa.pub | ssh root@123.123.123.123 "cat >> .ssh/authorized_keys"
```

#### Folder size recursively
```bash
du -sh ./* 2>/dev/null | sort -hr | grep -Ev '^0|^[0-9.]+K'
```

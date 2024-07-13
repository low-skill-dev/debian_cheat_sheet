### debian_cheat_sheet

#### After install
```
apt -y update && apt -y upgrade && apt -y full-upgrade && apt -y dist-upgrade
```

#### Copy Win11 SSH key to the Debian server (copying is not working in PS, use CMD)
```
type $env:USERPROFILE\.ssh\id_rsa.pub | ssh root@stroyform.keenetic.pro "cat >> .ssh/authorized_keys"
```

#### Folder size recursively
```bash
du -sh ./* 2>/dev/null | sort -hr | grep -Ev '^0|^[0-9.]+K'
```

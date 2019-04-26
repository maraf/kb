# Samba

- Config file: `/etc/samba/smb.conf`.
- After changing config, restart service: `systemctl restart smbd.service`.

## Example share definition
```
[k8s]
   comment = Some description
   path = /path/to/folder
   create mask = 0774
   directory mask = 0774
   valid users = @users
   force group = users
   read only = no
```

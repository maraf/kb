# Server
To run server (or host), first install `nfs-kernel-server`.

```
apt-get update
apt-get install nfs-kernel-server
```

NFS uses RPC and sometimes (after installation) it may required the binding service.

```
systemctl restart rpcbind
```

To create share directory, edit `/etc/exports`.
Each line has this format.

```
directory_to_share    client(share_option1,...,share_optionN)
```

After editing, let service reload the configuration.

```
exportfs
```

# Client
To run client, first install `nfs-common`

```
apt-get update
apt-get install nfs-common
```

Than you can mount the share.

```
mount {host_ip}:/{host_share_path} /{client_share_path}
```

## Links

- https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nfs-mount-on-ubuntu-16-04
- https://www.cyberciti.biz/faq/how-to-ubuntu-nfs-server-configuration-howto/
- https://www.htpcguides.com/configure-nfs-server-and-nfs-client-raspberry-pi/

# Server
To run server (or host), first install `nfs-kernel-server`.

> This `nfs-kernel-server` points to the `nfs-server`.

```
apt-get update
apt-get install nfs-kernel-server
```

NFS uses RPC and sometimes (after installation) it may required the binding service.

```
systemctl restart rpcbind
```

Or sometimes it may help to restart NFS service itself.

```
systemctl restart nfs-kernel-server
```

To create share directory, edit `/etc/exports`.
Each line has this format.

```
directory_to_share    client(share_option1,...,share_optionN)
```

After editing, let service reload the configuration.

```
systemctl restart nfs-kernel-server
```

> Related command: `exportfs`.

## Reload changes to /etc/exports

```
exportfs -ra
```

-a     Export or unexport all directories.<br>
-r     Reexport   all   directories, synchronizing /var/lib/nfs/etab with /etc/exports and files under /etc/exports.d.

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

## Troubleshooting

1) Get more info from client:

```
mount -v -t ...
```

2) Get current status on server:

```
showmount -e 127.0.0.1
```

3) If RPC is not registered, shown from the above:

```
/etc/init.d/nfs-kernel-server restart
```

Maybe it will work with the `systemctl`, but I'm not sure.

## Error 111
May raise when host is not running well.

1) `service rpcbind restart`
2) `/etc/init.d/nfs-kernel-server restart`

## Links

- https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nfs-mount-on-ubuntu-16-04
- https://www.cyberciti.biz/faq/how-to-ubuntu-nfs-server-configuration-howto/
- https://www.htpcguides.com/configure-nfs-server-and-nfs-client-raspberry-pi/

# Setup linux connection using SSH-key from Windows

We will need [SSH on windows](ssh-on-windows.md).

Now, to we need to generate an ssh key.

```
ssh-keygen
```

Our key will be generated under a current windows user folder, in a subfolder `.ssh`. <br />
Now we need to copy this key to a linux machine, to a file `.ssh/authorized_keys` under user's profile. <br />
(Replace {UserName} with our username on Windows and the second one on the linux, {LinuxAddress} with address of linux machine).

```
type C:\Users\{UserName}\.ssh\id_rsa.pub | ssh {UserName}@{LinuxAddress} 'cat >> .ssh/authorized_keys'
```

> The last argument to the `ssh` command will be always passed to the remote machine and than the connection will be closed.

Now, we can connect to the linux machine without typing password, using only a `{UserName}@{LinuxAddress}`.

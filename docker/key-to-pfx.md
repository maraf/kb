# Convert .key (and .crt) to .pfx

We will use `nginx` docker image, as it has `openssl` installed.

Prepare a folder containing two files: `tls.key` and `tls.crt`.
Than run:

```
docker run -v {host_path}:/cert --rm -it nginx openssl pkcs12 -export -out /cert/tls.pfx -inkey /cert/tls.key -in /cert/tls.crt -certfile
 /cert/tls.crt
```

An example of `{host_path}` is `$PWD/MyCert`, a folder under current path.

You will be prompted to set a password for `.pfx`.

If everything passes, the folder will contain 3 files.

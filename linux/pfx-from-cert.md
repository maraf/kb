# Create PFX certification from .crt and .key

```
openssl pkcs12 -export -out tls.pfx -inkey tls.key -in tls.crt -certfile tls.crt
```

On fresn ubuntu (container), first install `openssl`.

```
apt-get update
apt-get install openssl -y
```

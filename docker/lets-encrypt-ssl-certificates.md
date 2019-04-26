# Let's Encrypt SSL certificates

There are some prebuilt images, but none of these work on ARM.
- https://hub.docker.com/r/certbot/certbot
- https://github.com/samoshkin/docker-letsencrypt-certgen

## Manual certificate generation inside container

1) Use any linux distro (eg. Ubuntu).
2) Ensure these tools are installed: `wget`, `nano`, `nginx`.
3) Configure nginx to handle requests for requested domain. Use separate configuration file linked to sites-enabled.
4) Download certbot-auto `wget https://dl.eff.org/certbot-auto`, make executable `chmod a+x certbot-auto`.
5) Generate your certificate using `./certbot-auto --nginx certonly`
6) Using `tar` and `scp` copy `*.pem` files from `/etc/letsencrypt/archive/{domain}`.

## My custom image for ARM

Repo - https://github.com/maraf/certbot-arm <br>
Dockerfile - https://github.com/maraf/certbot-arm/blob/master/Dockerfile

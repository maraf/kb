# Let's Encrypt SSL certificates

There are some prebuilt images, but none of these doesn't work on ARM.
- https://hub.docker.com/r/certbot/certbot
- https://github.com/samoshkin/docker-letsencrypt-certgen

## Manual certificate generation inside container

1) Use any linux distro (eg. Ubuntu).
2) Ensure these tools are installed: `wget`, `nano`, `nginx`.
3) Configure nginx to handle requests for requested domain. Use separate configuration file linked to sites-enabled.
4) Download certbot-auto `wget https://dl.eff.org/certbot-auto`, make executable `chmod a+x certbot-auto`.
5) Generate your certificate using `./certbot-auto --nginx certonly`
6) Using `tar` and `scp` copy `\*.pem` from `/etc/letsencrypt/archive/{domain}`.

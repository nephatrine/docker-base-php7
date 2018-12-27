[Git Repo](https://code.nephatrine.net/nephatrine/docker-base-php7) |
[DockerHub](https://hub.docker.com/r/nephatrine/base-php7/) |
[unRAID Template](https://github.com/nephatrine/unraid-docker-templates)

# PHP7 Base Container

This is not intended to be used directly. It is intended to be used as a base image by other docker containers hosting specific PHP applications.

- [docker-nginx-ssl](https://code.nephatrine.net/nephatrine/docker-nginx-ssl)
- [PHP 7.2](http://www.php.net/)

## Configuration

- ``{config}/etc/crontab``: Crontab Entries
- ``{config}/etc/logrotate.conf``: Logrotate General Configuration
- ``{config}/etc/logrotate.d/*``: Logrotate Per-Application Configuration
- ``{config}/etc/mime.types``: NGINX MIME Types
- ``{config}/etc/nginx.conf``: NGINX General Configuration
- ``{config}/etc/nginx.d/*``: NGINX Per-Site Configuration
- ``{config}/etc/php.d/*``: PHP Extension Configuration
- ``{config}/etc/php.ini``: PHP General Configuration
- ``{config}/etc/php-fpm.conf``: PHP-FPM General Configuration
- ``{config}/etc/php-fpm.d/*``: PHP-FPM Per-Site Configuration
- ``{config}/ssl/live/{site}/``: SSL/TLS certificates

Certbot is included for requestung SSL certificates but you are better off just enabling HTTP from these containers and then using a single [docker-nginx-ssl](https://code.nephatrine.net/nephatrine/docker-nginx-ssl) container as a reverse proxy and handling all the HTTPS/SSL configuration there.

## Ports

- **80/tcp:** HTTP Port
- **443/tcp:** HTTPS Port

## Variables

- **ADMINIP:** Administrative Access IP
- **DNSADDR:** Resolver IPs (Space-Delimited)
- **PUID:** Volume Owner UID
- **PGID:** Volume Owner GID
- **SSLEMAIL:** LetsEncrypt Email Address
- **SSLDOMAINS:** LetsEncrypt (Sub)domains (comma-delimited)
- **TZ:** Time Zone

## Mount Points

- **/mnt/config:** Configuration/Logs
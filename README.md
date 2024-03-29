# CardNames

<p align="center">
  <img src="./public/bg.jpg" alt="CardNames" />
</p>

[![Bun Vite Deploy](https://github.com/sistematico/cardnames/actions/workflows/deploy.yml/badge.svg)](https://github.com/sistematico/cardnames/actions/workflows/deploy.yml)

Jogo de tabluleiro ao estilo "CodeNames".

## Nginx

```shell
server {
    listen 443 ssl;
    listen [::]:443 ssl;

    ssl_certificate         /etc/letsencrypt/live/dominio.com/fullchain.pem;
    ssl_certificate_key     /etc/letsencrypt/live/dominio.com/privkey.pem;

    server_name dominio.com;
    root /var/www/dominio.com/dist/public;
    
    include conf.d/cache.conf;
    include conf.d/errors.conf;
    include conf.d/vite.conf;
}
``` 

## SystemD

```shell
[Unit]
Description=CardNames Back-end
After=network.target

[Service]
User=nginx
WorkingDirectory=/var/www/dominio.com
ExecStart=/home/nginx/.bun/bin/bun /var/www/dominio.com/server/index.ts
Restart=always
RestartSec=5s

[Install]
WantedBy=multi-user.target
``` 


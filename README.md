# CardNames

Jogo de tabluleiro ao estilo "CodeNames".

## Nginx

```shell
server {
    listen 443 ssl;
    listen [::]:443 ssl;

    ssl_certificate         /etc/letsencrypt/live/dominio.com/fullchain.pem;
    ssl_certificate_key     /etc/letsencrypt/live/dominio.com/privkey.pem;

    server_name dominio.com;
    root /var/www/dominio.com/apps/site/dist;
    
    include conf.d/cache.conf;
    include conf.d/errors.conf;
    include conf.d/vite.conf;
}
``` 
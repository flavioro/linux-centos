# nginx

access root
```
sudo su
```

Install nginx
```
sudo apt install nginx
```

After install, access folder, file configuration (default)
```
/etc/nginx/sites-enabled
```

### Example file default
```
server {
  server_name shoparch.com.br www.shoparch.com.br;
  location / {
          proxy_pass http://localhost:3000;
          proxy_http_version 1.1;
          proxy_set_header Upgrade $http_upgrade;
          proxy_set_header Connection 'upgrade';
          proxy_set_header Host $host;
          proxy_cache_bypass $http_upgrade;
  }
listen [::]:443 ssl ipv6only=on; # managed by Certbot
listen 443 ssl; # managed by Certbot
ssl_certificate /etc/letsencrypt/live/shoparch.com.br/fullchain.pem; # managed by Certbot
ssl_certificate_key /etc/letsencrypt/live/shoparch.com.br/privkey.pem; # managed by Certbot
include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot
}
server {
  server_name projetadas.com.br www.projetadas.com.br;
  location / {
          proxy_pass http://localhost:4000;
          proxy_http_version 1.1;
          proxy_set_header Upgrade $http_upgrade;
          proxy_set_header Connection 'upgrade';
          proxy_set_header Host $host;
          proxy_cache_bypass $http_upgrade;
  }
listen 443 ssl; # managed by Certbot
ssl_certificate /etc/letsencrypt/live/projetadas.com.br/fullchain.pem; # managed by Certbot
ssl_certificate_key /etc/letsencrypt/live/projetadas.com.br/privkey.pem; # managed by Certbot
include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot
}
server {
if ($host = projetadas.com.br) {
  return 301 https://$host$request_uri;
} # managed by Certbot
  listen 80;
  server_name projetadas.com.br;
return 404; # managed by Certbot
}
server {
if ($host = shoparch.com.br) {
  return 301 https://$host$request_uri;
} # managed by Certbot
  listen 80 default_server;
  listen [::]:80 default_server;
  server_name shoparch.com.br;
return 404; # managed by Certbot
}
```

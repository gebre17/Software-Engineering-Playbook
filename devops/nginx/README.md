# Nginx Configuration

Nginx is a high-performance web server, reverse proxy, load balancer, and HTTP cache.

## Standard Reverse Proxy Configuration
Routing public traffic (port 80/443) to internal application runtimes (e.g., Gunicorn running on port 8000).

```nginx
server {
    listen 80;
    server_name example.com www.example.com;

    location /static/ {
        alias /var/www/static/;
    }

    location / {
        proxy_pass http://127.0.0.1:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

## SSL Configuration (Certbot / Let's Encrypt)
Recommended HTTPS configuration with TLS optimization.

```nginx
server {
    listen 443 ssl;
    server_name example.com;

    ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;

    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_prefer_server_ciphers on;
    ssl_ciphers HIGH:!aNULL:!MD5;
}
```

# Ghost easy deployment using Docker Compose

The easy [Ghost](https://ghost.org/) (https://github.com/docker-library/ghost) deployment using docker-compose.

You may need to set up Nginx (using proxy pass) if you have multiple application using different domains/ports in the server, or you can just set the port to 80.  

## How to run

- Clone this repository `git clone https://github.com/royryando/ghost-blog-deploy.git` or `git clone git@github.com:royryando/ghost-blog-deploy.git`
- Create .env file by copying the example `cp .env.example .env`
- Adjust environment variables inside .env file
- Run the container using `docker-compose up` or run in the background with `docker-compose up -d`
- Done. You can open the app `http://[your-host]/ghost` to get started

## Use with Nginx Reverse-Proxy

If you want to access the app using a domain, you need to add this to your nginx config file. You might need to adjust one/more parts with your current config.

```nginx
server {
    listen 80;
    server_name your-domain.com;

    client_max_body_size 50m;

    location / {
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header Host $http_host;
        proxy_pass http://127.0.0.1:8080;   # Use port defined in your .env
    }
}
```

## Backup & Restore

When you want to backup or restore the app you just need to save these directory:
- `./ghost-content/` -> Ghost content
- `./ghost-db/` -> Ghost mysql data

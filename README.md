# Ghost easy deployment using Docker Compose

The easy [Ghost](https://ghost.org/) (https://github.com/docker-library/ghost) deployment using docker-compose.

You may need to set up Nginx (using proxy pass) if you have multiple application using different domains/ports in the server, or you can just set the port to 80.  

## How to run

- Clone this repository `git clone https://github.com/royryando/ghost-blog-deploy.git` or `git clone git@github.com:royryando/ghost-blog-deploy.git`
- Create .env file by copying the example `cp .env.example .env`
- Adjust environment variables inside .env file
- Run the container using `docker-compose up` or run in the background with `docker-compose up -d`
- Done. You can open the app `http://[your-host]/ghost` to get started

## Backup & Migration

When you want to backup or migrate the app you just need to save these directory:
- `./ghost-content/` -> Ghost content
- `./ghost-db/` -> Ghost mysql data

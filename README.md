# Ghost easy deployment using Docker Compose

The easy [Ghost](https://ghost.org/) (https://github.com/docker-library/ghost) deployment using docker-compose.

You may need to set up Nginx (using proxy pass) if you have multiple application using different domains/ports in the server, or you can just set the port to 80.  

## How to setup

- Clone this repository`git clone https://xxx`
- Create .env file by copying the example `cp .env.example .env`
- Adjust environment variables inside .env file
- Run the container using `docker-compose up` or run in the background with `docker-compose up -d`

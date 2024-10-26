# Docker Harbour

Docker Harbour is a Docker Compose set-up for deploying [Portainer](https://www.portainer.io) with [Caddy](https://caddyserver.com) as a reverse proxy.

## Environment Variables

Before being able to deploy this stack, you are required to pass the following environment variables. You may rename `.env.example` to `.env`, and change the existing values to your liking. By default, you will be able to deploy the stack on a local device without having to modify any of these values.

### `CADDY_EMAIL`

The email address used for creating an ACME account with your certificate authority. You are only required to change this value if you are going to deploy this stack on a remote server. This will allow you to access Portainer's user interface via HTTPS.

### `PORTAINER_DOMAIN`

The domain on which you will be able to access the Portainer user interface and Edge Agent. This can either be a domain like `example.com`, or `localhost` if you are deploying this stack locally. The subdomains are automatically set to `portainer` and `edge`.

### `PORTAINER_EDITION`

The edition of Portainer you would like to use. You can choose between Portainer Community Edition (`ce`) or Portainer Business Edition (`ee`).

## Caddy

This stack utilises the [Caddy-Docker-Proxy](https://github.com/lucaslorentz/caddy-docker-proxy) plugin, which allows you to use [Caddy](https://caddyserver.com) as a reverse proxy for Docker containers via labels. Please take a look at their repository for more information on how to use these labels with Caddy.

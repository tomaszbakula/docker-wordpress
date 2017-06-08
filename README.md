# Docker WordPress

The docker local development environment for WordPress.

[Configuration details](https://coderwall.com/p/qknu2g/local-docker-development-with-virtual-hosts)

## First boot guild
1. Create network for reverse proxy

  `docker network create --driver bridge reverse-proxy`
  
2. Run reverse proxy service

  `docker run -d --name nginx-proxy --net reverse-proxy -p 80:80 -v /var/run/docker.sock:/tmp/docker.sock:ro jwilder/nginx-proxy`

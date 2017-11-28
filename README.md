# BakulaPress

The Docker local development environment for WordPress,<br>
allowing you to serve your projects under project-name.localhost domain.

## First boot guide
### 1. Create a reverse proxy network

`docker network create --driver bridge reverse-proxy`

### 2. Run a reverse proxy service

`docker run -d --name nginx-proxy --net reverse-proxy -p 80:80 --restart unless-stopped -v /var/run/docker.sock:/tmp/docker.sock:ro jwilder/nginx-proxy`

### 3. Configure the project

Open up *docker-compose.yml* file, search and replace all occurrences of **example** in the file to the project name of your choice. Save changes and run `docker-compose up` in the terminal.

---
If you would like to serve your websites with different suffix then .localhost you can use [dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html). Here is [a guide](https://coderwall.com/p/qknu2g/local-docker-development-with-virtual-hosts) how to do this.
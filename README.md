# wp-docker-compose-dev
WordPress Development Environment Using Docker

## Install Docker Compose
You will either need 
- Docker Engine + Docker-Compose
- OR Docker Desktop (includes both)

## Clone environment repo
### Enter the project directory
*You can use whatever directory. Here we'll use `/Dev/Docker/test` in your home folder.*
`cd ~/Dev/Docker/test`

### Clone repo
`git clone https://github.com/hegemanjr/wp-docker-compose-dev.git`

## Add domain entries to your hosts file
### Open hosts file for editing
`sudo nano /etc/hosts`

### Add your desired domains to the hosts file, pointing to localhost
```
# Docker Dev
127.0.0.1 uwsa.test example.local example-one.local example-two.local
```

### Add your desired domains to the Caddyfile
*You will need to configure the proxy server to use your domains*


### Open Caddyfile file for editing
`nano ./Caddyfile`

### Add an entry for each of your desired domains
```
example.local {
        tls internal
        reverse_proxy wordpress:80
}
```

## Start docker
`docker-compose up -d`

## Stop docker
`docker-compose down --remove-orphans`




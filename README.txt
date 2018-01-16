[Træfik](https://traefik.io/) is a modern HTTP reverse proxy which will be used to setup multiple websites in a single host with ease.

***READ [How to Use Traefik as a Reverse Proxy for Docker Containers on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-use-traefik-as-a-reverse-proxy-for-docker-containers-on-ubuntu-16-04)***

**Usage**
```
git clone git@github.com:valuebound/traefik.git
cd traefik
docker run -d  -v /var/run/docker.sock:/var/run/docker.sock -v $PWD/traefik.toml:/traefik.toml -v $PWD/acme.json:/acme.json -p 80:80 -p 443:443 -l traefik.frontend.rule=Host:monitor.codespace.io -l traefik.port=8080 --network traefik_proxy --name traefik traefik:1.3.6-alpine --docker
```

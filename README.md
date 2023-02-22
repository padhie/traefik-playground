# traefik-playground
little Repository to testing and using traefik for the daily workflow


## traefik container 
Subnet is `172.16.0.0/16` - traefik use `172.16.1.x`   
You can set the last IP-Ranges for Projects IPs


## for your projects
Add to your Project docker-compose:
```bash
services:
    foobar:
        labels:
            - "traefik.http.routers.your-host.rule=Host(`your-host.localhost`)"
        networks:
            traefik:
                ipv4_address: 172.16.2.1

networks:
    traefik:
        name: traefik
        external: true
```
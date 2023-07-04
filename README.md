# nginx-certbot-docker
Minimal setup for an nginx server running in docker and secured with certbot

## Overview
1. Create a server and configure it with docker and compose
    - Ensure the server is configured with an ipV6 address
2. Register and configure a domain
3. Configure a DNS server to point the domain to the ipv4 and ipv6 addresses of the server
    - Note: these IP addresses may change and this will break the resolution chain.
    - Services to prevent these issues exist but are out-of-scope here
4. `ssh` into the server and clone this repo
5. `cd` into the repo
6. Run the docker containers `docker compose up`
7. Get the id of the nginx container `docker ps`
8. Exec into the nginx container `docker exec -it [container-id] ash`
9. Run certbot `certbot --nginx -d yourdomain.com -d www.yourdomain.com`

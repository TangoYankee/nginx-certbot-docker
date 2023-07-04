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
6. Run the docker containers `docker compose up --build -d`
7. Get the id of the nginx container `docker ps`
8. Obtain the letsencrypt certificates `docker exec ${CONTAINER_ID} certbot -n -m ${CONTACT_EMAIL} -d ${DOMAINS} --nginx`
9. Start the auto-renew cron job `docker exec ${CONTAINER_ID} crond`

follow this tutorial: `https://www.digitalocean.com/community/tutorials/how-to-use-traefik-v2-as-a-reverse-proxy-for-docker-containers-on-ubuntu-20-04`

1. `docker network create web`
2. `touch acme.json`
3. `chmod 600 acme.json`
4.  `docker run -d -v /var/run/docker.sock:/var/run/docker.sock -v $PWD/traefik.toml:/traefik.toml -v $PWD/traefik_dynamic.toml:/traefik_dynamic.toml -v $PWD/acme.json:/acme.json -p 80:80 -p 443:443 --network web --name traefik traefik:v2.2`
5. `docker-compose up -d`
6. `export WORDPRESS_DB_PASSWORD=secure_database_password
   export MYSQL_ROOT_PASSWORD=secure_database_password`
### Setup docker on Debian 8.1

Install notes: https://docs.docker.com/install/linux/docker-ce/debian/#install-using-the-repository

Docker CLI: https://docs.docker.com/engine/reference/run/

Script that installs docker-ce: `setup_docker_debian.sh`

### Build&Run COLX docker container

Pre: `ColossusCoinXT.conf MUST be available under link COLX_CONF_URL as pointed out in the Dockerfile`

Build container: `sudo docker build --tag colx:1.0.3 .`

Run container: `docker run -d --name colx.cont colx:1.0.3`

See if it is up: `docker ps -a`

Shell in the container: `docker exec -it colx.cont /bin/bash`

Test RPC: `colx-cli -rpcuser=colx -rpcpassword=<from config file> help`

Stop container: `docker stop colx.cont`

Delete container: `docker rm colx.cont`
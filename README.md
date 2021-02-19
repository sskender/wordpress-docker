# Wordpress Docker

#### Run a scalable and a high availability Wordpress website in Docker swarm

### Running

Run stack:

```bash
docker stack deploy --compose-file docker-compose.yml wpstack
```

Re-scale wordpress service:

```bash
docker service scale wpstack_wordpress=4
```

Remove stack:

```bash
docker stack rm wpstack
```

### Features

- encrypted overlay network
- wordpress volume mounted to a shared persistance storage array
- database performance configured for a server with 4CPUs and 8GB of RAM

#### Disclaimer

This configuration is intended to run behind a proxy with SSL and a firewall.

### Model

Image is showing the stack running on three Ubuntu demo servers. Database is on the manager node, and two wordpress instances on each worker node.

![Model](model.png)

#### Help guides:

- https://maddevs.io/blog/deploy-and-scale-wordpress-with-docker-cloud-swarm-mode/
- https://hackernoon.com/architecting-a-highly-available-and-scalable-wordpress-using-docker-swarm-traefik-glusterfs-a69186e9f0e
- https://thenewstack.io/tutorial-create-a-docker-swarm-with-persistent-storage-using-glusterfs/
- https://www.digitalocean.com/community/tutorials/how-to-configure-the-linux-firewall-for-docker-swarm-on-ubuntu-16-04

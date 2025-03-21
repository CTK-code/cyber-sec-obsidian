###### [run](https://docs.docker.com/reference/cli/docker/container/run/): 
runs the designated container image
```bash
docker run -d -p <hostport>:<container-port> <image-name>
	-d: run in detached (command runs in background)
	-p: define the ports to assosciate to
ex: docker run -d -p 81:80 docker/getting-started

docker run -d -e NODE_ENV=development -e url=http://localhost:3001 -p 3001:2368 -v ghost-vol:/var/lib/ghost/content ghost
	-e: sets the NODE_ENV environment variable to development same with the url
	-v: <volume-name>:<conatiner-file-system-location> mounts a volume to the container filesystem if exists or creates one if not.
	
```
###### [exec](https://docs.docker.com/reference/cli/docker/container/exec/): 
allows a single command to be run in the docker container at CONTAINER_ID 
```bash
docker exec CONTAINER_ID netstat -ltnp

docker exec -it bba631e9a35f  /bin/sh
	-i: makes exec interactive
	-t: gives a tty (teletypewriter)
	/bin/sh: what shell we want to use
```

###### [volume]():
Allows to manipulate and view docker volumes. Lots of stuff.
```bash
creating a volume
docker volume create <volume-name>
docker volume create ghost-vol

removing a volume:
docker volume rm <volume-name> 

  create      Create a volume
  inspect     Display detailed information on one or more volumes
  ls          List volumes
  prune       Remove unused local volumes
  rm          Remove one or more volumes
```

###### [ps]():
Lists the containers that are on your machine. Can be in various states of running, or not.
```bash
docker ps
	-a: shows all containers, not just those running
```

###### [restart]():
Restarts the designated container.
```bash
 docker restart <container-id | container-name>
```

###### [rm](https://docs.docker.com/reference/cli/docker/container/rm/):
removes a conatiner
```bash
	docker rm <container-id | container-name>

handy command to remove all docker containers and their associated volumes. use at your own risk
	docker rm -v -f $(docker ps -qa)
		-v: removes assosciated volumes
		-f: removes even running containers
```

###### [network](https://docs.docker.com/reference/cli/docker/network/):
Series of commands that allow us to create a network for our docker containers
```bash
creating a network:
	docker network create <name-of-network>
	docker network create caddytest
ls: list networks
```
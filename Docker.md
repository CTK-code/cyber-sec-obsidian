###### [run](https://docs.docker.com/reference/cli/docker/container/run/): 
runs the designated container image
```
docker run -d -p <hostport>:<container-port> <image-name>
	-d: run in detached (command runs in background)
	-p: define the ports to assosciate to
ex: docker run -d -p 81:80 docker/getting-started
```
###### [exec](https://docs.docker.com/reference/cli/docker/container/exec/): 
allows a single command to be run in the docker container at CONTAINER_ID 
```
docker exec CONTAINER_ID netstat -ltnp

docker exec -it bba631e9a35f  /bin/sh
	-i: makes exec interactive
	-t: gives a tty (teletypewriter)
	/bin/sh: what shell we want to use
```

###### [volume]():
Allows to manipulate and view docker volumes. Lots of stuff.
```
docker volume create <volume-name>
docker volume create ghost-vol

```
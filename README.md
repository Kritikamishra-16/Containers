# Commands to run the server inside docker container 

Create a DockerFile

Clean up the whole system and delete every image, container, cache etc
```
docker system prune -a
```

Build a docker file and create an image
(execute this command either from the directory where docker file is present, or replace . with path to dockerfie)
```
docker build -t <tag_name> .
```

Run a container from the image
(-it opens an interactive console and --init helps you to control the process of the container from host machine and --publish is to publish/ exposing container's 3000 port to host 3001 port so that we can access it locally until and unless we explicitly configure the communication between host and container , container will be isolated)
```
docker run -it --init -publish <host_port>:<container_port> <image_name>

docker run -it --init -p 3001:3000 my-express-server (shorthand)

docker run -it --init -P my-express-server (when we expose any port in docker file itself then it automatically tunnels conatiners 3000port to host's random post which can be seen using docker ps)
```

Bind mount project with docker conatiner
```
docker run -it --init -p 3001:3000 -v "$(pwd)":/developer/nodejs/node-bind-mount-project <image_name>
```

Add Docker vloume so that data persists even if containeris turn down
```
docker volume api-gateway-node-modules
docker run -it --init -publish 3001:3001 -v "($pwd)":/developer/nodejs/api-gateway  -v api-gateway-node-modules:/developer/nodejs/api-gateway/node_modules <image_tag>
```


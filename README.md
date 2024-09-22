# Commands to run the nodejs server inside docker container 

```
 1. Create a DockerFile
 
 2. docker build -t my-express-server .   -> -t to give tag name for the image and . is the current directory
 
 3. docker run -it --init --publish 3001:3000 my-express-server -> -it opens an interactive console and --init helps you to control the process of the container from host machine and --publish is to publish/ exposing container's 3000 port to host 3001 port so that we can access it locally until and unless we explicitly configure the communication between host and container , container will be isolated
 
 3. docker run -it --init -p 3001:3000 my-express-server -> shorthand
 
 4. docker run -it --init -P my-express-server -> when we expose any port in docker file itself then it automatically tunnels conatiners 3000port to host's random post which can be seen using docker ps
 
```

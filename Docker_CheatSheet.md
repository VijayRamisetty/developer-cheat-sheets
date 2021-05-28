# Docker Help Commands
# version
docker --version
docker version
docker version --format json
docker version --format '{{json .}}'
docker version --format '{{.Server.Version}}'

# getting-started
docker run -d -p 80:80 docker/getting-started
docker ps
docker scan getting-started

# start
docker start [CONTAINER-ID]
docker start [CONTAINER-NAME]

# stop
docker stop [container-id]
docker stop [container-name]

# pull
docker pull [IMAGE]:[TAG]
docker pull mysql:lastest
docker pull ubuntu

# Images 
docker images
docker image ls 
docker image rm [IMAGE-ID]
docker rmi [Image-ID]

docker image history docker/getting-started

# Run
docker run --name [DESIRED_NAME_OF_CONTAINER] 
docker container run --name [DESIRED_NAME_OF_CONTAINER] -p 5000:80 -d [IMAGE]:[TAG]
docker run --name  container-mysql -e MYSQL_ROOT_PASSWORD=ramisetty -p 3306:3306 -d mysql:latest

# exec
docker exec -it [CONATAINER_NAME] [COMMAND_YOU_WANT_TO_RUN] 
docker exec -it container-mysql mysql -uroot -p

# Container
docker ps 
docker ps -a
docker ps -aq
docker container ls 
docker container ls -a  
docker container ls -all

# network
docker network ls 

# logs
docker container logs --tail 100 [CONTAINER-NAME/CONTAINER-ID]


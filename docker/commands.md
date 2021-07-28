* docker build -t getting-started .
    * -t: tag
    * .: Dockerfile path
    * getting-started: name
* docker run -dp 3000:3000 getting-started
    * -dp: detachable + port
    * getting-started: image name
* docker image ls
* docker ps: show all running containers
* docker tag getting-started allen0346/getting-started
    * tag: create a new image from getting-started image and name it ` allen0346/getting-started:latest`
*  docker push allen0346/getting-started
    * push local allen0346/getting-started image to online repo "getting-started" from allen0346 account
* docker ps -sd
    * show size of all containers
* docker exec <container-id> cat /data.txt
    * cat: command
    * exec: get into container and run some commands
* docker volume create todo-db
* docker run -dp 3000:3000 -v todo-db:/etc/todos getting-started
* docker rm -f <docker id>
* docker volume inspect <volume name>

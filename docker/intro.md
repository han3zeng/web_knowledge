## Docker

#### Overview
* Docker Image: it is just a static file system template
* Docker Container: running instance which based on a Docker Image
* multi-layers
    * run the Docker Container and save the state create a new image layer on top of the initial image layer
* [Docker is lightweight](https://phoenixnap.com/kb/docker-image-vs-container)
    * virtualize at app layer
    * traditional VM virtualize at hardware layer


#### Steps
1. `docker build` a system through docker file
2. get docker image
3. run docker container based on the image -> run the app

## References
* [ref1](https://phoenixnap.com/kb/docker-image-vs-container)

# docker-learn

First implementation to understand how to use docker

Steps involved to setup on Windows:
1. Download Docker Desktop for Windows from https://hub.docker.com/editions/community/docker-ce-desktop-windows 

## Steps used to setup docker, create image and push to docker repository
1. Create a new Dockerfile
2. Create requirements.txt file with packages/dependencies required for running the code
3. Create app.py to run a sample HTTP API to return Hello World with instance details.
4. Build docker image with command: docker build --tag=docker-learn-python .
5. Create a tag for docker image to upload to repository: docker tag docker-learn-python pankaj1620/docker-learn:python
6. Push the image to repository: docker push pankaj1620/docker-learn:python

## Bring up multiple instances with load balancing(Services)
1. Create new docker-compose.yml file with configuration for multiple instances
2. Initialize swarm with command: docker swarm init
3. Deploy image to create instances(Stack): docker stack deploy -c docker-compose.yml <stack_name>
4. To list stack: docker service ps <stack_name>_web
5. To remove stack and bring down apps: docker stack rm <stack_name>
6. To exit swarm: docker swarm leave --force

## How to
1. Create image: docker build --tag=docker-learn-python .
2. List local docker images: docker image ls [-a]
3. Run docker image: docker run -p 9001:80 docker-learn-python
4. List running images: docker container ls
5. Stop docker app: docker container stop <pid>
6. Run docker image from repository: docker run -p 9001:80 pankaj1620/docker-learn:python 

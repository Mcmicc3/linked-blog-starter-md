![[Pasted image 20241117160654.png]]

## Download containers from Github
```docker
git clone https://github.com/docker/welcome-to-docker
```

After you downloaded an image, you need to build it

## Build a Docker Image
```docker
docker build -t welcome-to-docker .
```
- The -t flag tags your image with a name 
- The '.' lets docker know where to find the dockerfile

You can view files that makeup the container right from Docker Desktop

You can also download images (Dockerfiles?) from hub.docker.com
- You can download images from the website, or you can type ctrl + k, and download it from Dockerfiles.

## Viewing running containers
```docker
docker ps
```

## Viewing downloaded images
```docker
docker image ls
```
## Running several containers at once
Some dockerfiles compile images made of several docker containers.  To run them all at once you need to run the docker compose command
- Look for a compose.yaml file in your directory
```docker
docker compose up -d
```
- The -d flag tells docker compose to run in detached mode

**Make sure each container has a unique port number**

## Containerizing your applications
If you want your application to run in a container, you need to create a Dockerfile to define your image and a compose.yaml file to define how to run it. 
To create these files, you can run *docker init*. Run this command in a project folder, and Docker will create all the required files needed.
```docker
docker init
```
You may need to look up the [Dockerfile reference⁠](https://docs.docker.com/engine/reference/builder/ "https://docs.docker.com/engine/reference/builder/") and [Compose file reference⁠](https://docs.docker.com/compose/compose-file/ "https://docs.docker.com/compose/compose-file/") in our documentation. Sometimes there's some assembly required. 

## Persist data between applications
Docker isolates all content, code, and data in a container from your local filesystem. This means, that when you delete a container within Docker Desktop, all the content within it is deleted.

Sometimes you may want to persist data that a container generated. This is when you can use volumes.
![[Pasted image 20241117162724.png]]

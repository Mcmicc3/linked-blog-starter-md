# CLI Shortcut

docker build -t welcome-to-docker .
- Builds a freshly downloaded dockerfile to create an image. 

docker compose up -d
- Used to run several containers at once. (Some containers are made of several smaller containers?)

docker image ls
- lists downloaded images

docker rmi {image_name_or_id}
- This deletes *images*, not containers

docker container ls -a
- This displays containers
- The '-a' option displays stopped containers too

docker rm {container_id_1}
- This will delete containers, *not images*
- It will only work if the container isn't running. 

docker ps
- Displays running containers

docker stop <container_id_1> <container_id_2> <container_id_3>
- This is how you stop multiple containers. 

docker stop $(docker ps -q)
- Stops all running containers at once

docker init
- Attempts to create a dockerfile to develop a container for your application

## Tips
It's recommended to stop a container before deleting it. 

Docker won't let you delete an image if there are containers associated with that image. *Even if they aren't running*. 

###### Making sense of ports in docker
docker run -d -p 3000:8080 <image_name> && Start-Process http://localhost:3000
- **`-p 8080:80`**: Maps port `80` in the container to `8080` on your local machine.
- The -d option is for detached mode, allowing us to keep using the terminal by pushing the container in the background. 

running an image will either create a new instance of that image to build a new container, or it will create the first instance of that image and build a container

starting a container (or running), will start only that specific instance.

# Understanding Docker

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

If you want to persist data **even after a container is deleted,** you can use a volume. A volume is a location in your local filesystem, managed by Docker.
![[Pasted image 20241117162856.png]]

#### Adding Volumes to Compose
To add a volume to this project, simply go to the **compose.yaml** file and uncomment the following lines:
![[Pasted image 20241117163046.png]]
###### Digging Deeper
The **volumes** element that is nested in **todo-database** tells Compose to mount the volume named **database** to **/data/db** in the container for the **todo-database** service.

The top-level **volumes** element defines and configures a volume named **database** that can be used by any of the services in the Compose file.

Now, no matter how often you delete and restart the container, your data is persisted and accessible to any container on your system by mounting the database volume. Docker will check for a volume and create one if there is none present.

## Accessing your local folder from a container
**Container data is isolated from your local folders**
Docker isolates all content, code, and data in a container from your local filesystem.

Sometimes you may want the container to access a directory on your system. This is when you use *bind mounts*.



# Questions
Why would someone delete an instance of a container, but keep the same image? Why not change the image (if needed), and restart the container?
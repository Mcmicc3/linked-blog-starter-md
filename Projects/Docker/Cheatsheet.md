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
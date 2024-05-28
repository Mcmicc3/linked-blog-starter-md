
# What is gVisor
- Application kernel, written in Go. 
- Isolated sandbox container
- Google
- Includes and Open Container Initiative (OCI) runtime called runsc
	- Integrates with Docker and Kubernetes
- Allows you to run applications (code) in a safe environment
- It handles systemcalls between the container and the host kernel
-  Secure, lightweight, 

Limitation issues
- As of right now it handles ( x out of x systemcalls)
- Compatability issue for some commands
- Limitations compared to other runtimes in terms of performance and compatability with certain applications.

# What is Docker
- Helps developers build, share, run, and verify applications anywhere - without tedious environmnet confirguration or management. 
- Docker Images, create multiple containers
	- Docker Images are read-only templates used to create containers. 
	- **Images** contain everything needed to run application, including the code, runtime, libraries, and dependencies.
	- Images are built from Dockerfiles, which are text files that define the steps needed to create the image. 
- Integrates well with existing tools (VS Code, CircleCI, Github)
- Run in any enviornment consistenetly from on-premises Jubernetes to AWS ECS, Azure,.....
- Docker provides a suite of development tools, services, trusted content, and automations, used individually or together, to accelerate the delivery of secure applications.
- Developing, shipping, running applications. 
- Lightweight, portable, and self-sufficient untis that package software and all its dependencies, allowing applications to run reliably across different computing environments. 
- Docker Engine is the core component of docker that enables container creation, management, and execution. 
	- server daemon ('dockerd').
	- It manages container lifecycles, and a command-line interface that allows users to interact with Docker. 
- Containers are lightweight, isolated environments created from Docker Images. Each container runs as a separate process on the host system, providing a consistent and predictable runtime environment for applications. 
- Widely adopted by developers, sysadmins, and organizations of all sizes.

# How to configure gVisor
Good fucking question

1. Choose an environment?
2. See the official documentation on gVisors website



# Problems I've run into


Mario Canales, [5/1/2024 1:35 PM]
# Docker:
## 1. What is Docker? : 
Docker is a popular open-source platform for developing, deploying, and running applications using containers, and is the Industry leader in containerization  

## 2. How are containers different from  virtual machines
- Virtual machines use hypervisors, which will have resources dedicated to it, Each VM includes a full copy of the operating system, along with the application and its dependencies
- Run on containerization platforms like Docker,  and it leverages the host operating systems kernel and creates user spaces for its containers, Containers don't need to reinstall the OS everytime are only bundled an application's code, libraries, and dependencies. Because of this They're Lightweight and Uses less resources, this gives us benefits of improved portability, isolation, and resource effienciency for running applications on site or in the cloud.

- Because of containerization, applications can run consistenetly on any system using a container engine, regardless of the operating system. 
-   This software can be used for building and deploying web applications among other things, and they integrates well with cloud providers like AWS, Azure, and Google Cloud
## 3. How popular is it?

  - Popular with developers and system administrators
  - 20 million users

## 4. Why talk about docker?
- Ontop of being the leading industry of containerization,
  - The CVE relates to docker

## 5. In order to understand the CVE better, we need to talk about runtimes, which is basically the engine Docker users in order to create containers.


# containerd:
1. What is it? Industry standard runtime, specifcally Dockers default container runtime
2. What is a runtime? 
3. There are high level runtimes and low level runtimes
4. High level manages everything except execution
5. Low level handles execution
6. Benefits
7. Secure as any software that is up to date, but just like any software, they have zero days, and it's not easy, but runtimes are avenue for container escape.
8. So what can we do?

# gVisor:
1. Alternative Runtime written in go language
2. Functions the same as containerd, except, it creates sandboxed isolated containers
3. What are isolated containers?
  1. An isolated container is a containerized application that runs in its own separate environment, cut off from other containers and the underlying operating system. This isolation provides several benefits: Security, Stability, and Resource Management
  2. Extra layer of isolation 
4. Intercepts 350 syscalls which are requests the application makes to the operation and handles them in user space (outside the host kernel), 274 syscalls have a full or partially intercept. There are currently 76 unsupported syscalls.
5. benefits in using this software
  1. Run untrusted code, very low possibility for container escape. 
  2. Confidentaly run containers in a public facing cloud
6. Some downsides
  1. Downsides: extra software and security checks can lead to Performance cost, some compatibility issues
    1. Most of the common utilities are supported but not all. Could lead to compatibility issues. 
7. Why we chose this tool for 
  - Basis of our project
 - Testing this softwares effectivness against container escapes.
8. Next we'll explore the CVE's we're testing against this software

Mario Canales, [5/1/2024 1:35 PM]
# Issues:
1. Start by talking about our original project
  1. Use a bare metal environment for 
2. Runs Docker, but failed to switch over to an alternate runtime
  - Possibly, don't mention the exact error
3. We tried it on our personal computers, and it works fine
4. So we looked more into it, and found that our server is using an xeon Intel processing chip
5. Looked into that processor, and found that it has a feature called TDX, which also creates isolated containers and virtualization, but it focuses on memory encryption and integrity for security-sensitive applications within virtual machines.
6. As of right now, there is no compatability between this TDX feature, and gVisor
7. Example of the compatibility issues in gVisor
8. {Bring up Shim?, or "We couldn't find the option to disable it, so insxtead we 
9. Shifted away from the bare metal environment, doing it on our computers instead.
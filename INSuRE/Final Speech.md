# Docker:  

Before we can go into detail about the leaky vessel exploits, we first need to discuss what docker is since it is the software leaky vessels is exploiting, as well as runtimes, in order to better understand how these exploits work.  
## 1. So What is Docker? : 
Docker is the Industry leader in containerization, and is a popular open-source platform for developing, deploying, and running applications using containers.

A Docker container, is a lightweight, self-contained unit that packages everything needed to run a piece of software, including the code, runtime, system tools, libraries, and settings. Containers give us the benefits of improved portability, isolation, and resource efficiency for running applications on site or in the cloud.

- Because of containerization, applications can run consistently on any system using a container engine, regardless of the operating system. 
-   Docker can also be used for building and deploying web applications, among other things, and it integrates well with cloud providers such as AWS, Azure, and Google Cloud

## 2. How popular is Docker?

It is estimated that Docker is used by over 20 million users, and is popular with developers, because of it's reproducibility, ensuring that applications behave the same in development, testing, and production, leading to more predictable results and easier debugging. It is also popular with system adminstrators for its abilility to produce rapid and consistent environments that can be used to provide a cost efficient solution to host their IT infrastructure.

## 3. Why are we talking about docker?
As mentioned before, the leaky vessels exploits are based on vulnerabilities found within Docker, therefore, we chose to use docker for our testing environments to explore these CVEs and conduct our container escape research.


## 4. In order to understand how the CVEs work, we now need to talk about runtimes, which is essentially the engine Docker users in order to create containers.


# containerd:
1. What is containerd, containerd is an Industry standard runtime, and specifcally Dockers default container runtime

3. They are defined through their high level and low level runtimes
4. The High level runtime, known as containerd, manages everything everything docker needs to spin a container, except for the execution process,
5. whereas the Low level runtime, refered to as runc, handles the execution process needed in creating containers. 
6. In essence, containerd and runc both work together to create a runtime for docker to execute containers
7. Benefits, fast and reliable
8. Secure as any software that is up to date, but just like any software, there's always the risk of a zero day attack, making runtimes an avenue for attack in executing a container escape. and as we will see in a moment, leaky vessels is an example of a vulnerability found in containerd to exploit docker a docker container.
9. So what can containerization environments do to possibly prevent these type of attacks in the near future?

# gVisor:

This brings us to the secure software solution this research is based on, gVisor, a secure runtime that was designed with the purpose of mitigating and preventing container escapes. 
## So what is gVisor?
1. Alternative Runtime written in go language, and is developed Google. 
2. Functions the same as containerd, except it was designed with security in mind, and it does this by creating what is called a sandboxed isolated container.
3. 
	1. A sandboxed isolated container is a containerized application that runs in its own separate environment, cut off from other containers and the underlying operating system. This isolation provides several **benefits: Security, Stability, and Resource Management**
	2. It basically adds an extra layer of isolation to your container. 
4. gVisor does this by intercepting services called syscalls, which are requests the application makes to the operating system, and is instead handled by gVisor in a user space which basically means it is handled outside of the host kernel. Of the 350 syscalls, gvisor can fully or partially intercept 274 of these syscalls leaving 76 unsupported, or in the progress of being supported.
5. Some benefits in using this software
	1. Run untrusted code, very low possibility for container escape. 
	2. Confidentaly run containers in a public facing cloud
6.  There are a few downsides in using gVisor. The first issue to consider is that the extra software and security checks  in gVisor may lead to a performance cost, and the second issue, is that most of the common utilities are supported by gVisor but not all of them such as netstat, sshd, and nmap. This may potentially lead to combability issues for some applications. 

## So why did we choose this tool?
  - We chose to conduct our research using gVisor because of the promises it makes in being an effective security method in containerization environments, and for it's adaptability to work in conjunction with Docker to help create secure work environments for it's millions of users. 
 
9. Next we will discuss the process used for conducting our research, as well as the environments we created to test against the leaky vessel CVEs

Next slide please.

# Issues:

Our second issue is in regards to a compatibility problem we ran into with gVisor. Our first idea was to have gVisor configured on a bare metal server with the ubuntu server operating system installed. After configuring Docker and gVisor, the server would report an error regarding a failure to read client sync files whenever we tried running a container using gVisor. After recreating the same testing environment on an AMD and Apple Silicon based personal computers, we found that they could successfully run gVisor containers. We then discovered that our server uses an XEON intel processor, which has a built-in security feature called TDX, which creates secure virtualized and container environments, but focuses on memory encryption and integrity for security-sensitive applications within virtual machines. As of May 2024, gVisor does not support TDX technology, and for this reason, we had to adjust our testing environment from our bare metal server, to an Ubuntu server running in a VM on  our personal computers. 



The third issue encountered in our research regards our attempt in creating a combined environment. Initially, we wanted to conduct a third experiment, where we would combine gVisor within a MicroVM, which is a technology that can isolate processes of an application into their own MicroVM while working in conjunction to support an application. This environment would potentially create an extra layer of security for users who want to run containers with security being the highest priority. After our success in exploring the leaky vessels CVE, we worked on configuring the gVisor-containerd-shim as suggested in gVisors documentation, but we then learned that the purpose for this configuration was instead used for another software regarding orchestration, and not microVMs. Because of our time restraint, we abandoned this idea and decided to focus soley on our gVisor and containerd docker environments. 



Lastly, for projects having secure containerization as it's highest priority, they can look into the applicability of running secure containers using gVisor within a popular microVM, such as kata or firecracker-containerd for an added extra layer of security.









## 2. How are containers different from  virtual machines
- Virtual machines use hypervisors, which will have resources dedicated to it, Each VM includes a full copy of the operating system, along with the application and its dependencies
- Run on containerization platforms like Docker,  and it leverages the host operating systems kernel and creates user spaces for its containers, Containers don't need to reinstall the OS everytime are only bundled an application's code, libraries, and dependencies. Because of this They're Lightweight and Uses less resources, this gives us benefits of improved portability, isolation, and resource efficiency for running applications on site or in the cloud.

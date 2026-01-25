![[Pasted image 20240119222800.png]]

# Questions for the group.
For the expected outcomes, can we pitch information that we think we may find? Say, testing a CVE on both a Sandboxed container, and a microVM, to see if there were any differences?

Since none of us have any real experience with containers, and it will be evident when noone mentions it in their list of skills. Should we include things like "this is a technology I'm interested in exploring and learning?"

## What is an OCI? CRI? Make sense of container runtimes


# What is the difference between a microVM and a VM?


# What is [gVisor](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjAla-i0OqDAxVwPEQIHSZvBVoQFnoECAMQAw&url=https%3A%2F%2Fgvisor.dev%2F&usg=AOvVaw3OK9atfTIm_re1XLPJS30C&opi=89978449)?
- Open source sandbox for container isolation
- Lightweight, and offers strong isolation.
- Sys calls sent to the host are trapped, and sent to the container instead, separating the container from the host 
- Works with kubernetes and docker

#### How does gVisor work?
gVisor implements the Linux API: **by intercepting all sandboxed application system calls to the kernel, it protects the host from the application**. In addition, gVisor also sandboxes itself from the host using Linux's isolation capabilities.
- gVisor uses the runtime: **runsc**

##### What is runsc?
What is runsc? **The entrypoint to running a sandboxed container** is the runsc executable. runsc implements the Open Container Initiative (OCI) runtime specification, which is used by Docker and Kubernetes. This means that OCI compatible filesystem bundles can be run by runsc .
- **runsc and runc are not the same**
- Five years ago, runsc and both runc could not run together on kubernetes, that could be different now [4:59](https://www.youtube.com/watch?v=6BWAhPPPPpQ)
#### What are the benefits of gVisor?
gVisor **protects your workload by intercepting system calls and emulating them in userspace**. This shields the host Linux kernel and the sandboxed application from each other, protecting against most Linux CVEs, container escape vulnerabilities, and making remote privilege-escalation attacks less impactful.

### What's the difference between gVisor and KVM?
What is the difference between gVisor and KVM?

![Platform Guide - gVisor](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR-aDGqi1S10uSqXokcfJz7oqzyfqBYOXNPbqHXvg5K&s)

**The KVM platform runs best on bare-metal setups**. While there is no virtualized hardware layer – the sandbox retains a process model – gVisor leverages virtualization extensions available on modern processors in order to improve isolation and performance of address space switches.
### [Platform Guide - gVisor](https://gvisor.dev/docs/architecture_guide/platforms/)



# What is Containerd?
1. Containerd is used by Docker, Kubernetes CRI, and a few other projects

#### [Firecracker-ContainerD](https://github.com/firecracker-microvm/firecracker-containerd)
Potential use cases of Firecracker-based containers include:

- Sandbox a partially or fully untrusted third party container in its own microVM. This would reduce the likelihood of leaking secrets via the third party container, for example.
- Bin-pack disparate container workloads on the same host, while maintaining a high level of isolation between containers. Because the overhead of Firecracker is low, the achievable container density per host should be comparable to running containers using kernel-based container runtimes, without the isolation compromise of such solutions. Multi-tenant hosts would particularly benefit from this use case.

###### Roadmap for containerD
To support the widest variety of workloads, firecracker-containerd has to work with popular container orchestration frameworks such as Kubernetes and Amazon ECS, so we will work to ensure that the software is conformant or compatible where necessary. The project currently allows you to launch a few containers colocated in the same microVM, and we are exploring how to raise the number of containers. We recently added support for configuring networking at the microVM level with CNI plugins and provide a CNI plugin suitable for chaining called "tc-redirect-tap". Our short term roadmap includes constraining or "jailing" the Firecracker VMM process to improve the host security posture. Our longer-term roadmap includes polishing, packaging, and generally making firecracker-containerd easier to run as well as exploring CRI conformance and compatibility with Kubernetes.

###### Usage
For detailed instructions on building and running firecracker-containerd, see the [getting started guide](https://github.com/firecracker-microvm/firecracker-containerd/blob/main/docs/getting-started.md) and the [quickstart guide](https://github.com/firecracker-microvm/firecracker-containerd/blob/main/docs/quickstart.md).

# Detecting Compromise?

## Software to determine compromise for containerization?
Grype: A tool for detecting vulnerabilities in container images by analyzing their software dependencies. **Anchore Engine**: A comprehensive container image inspection and vulnerability scanning tool. Clair: An open-source tool for static analysis of vulnerabilities in container images.Nov 9, 2023
[**Top Container Security Tools for 2024 - Practical DevSecOps**](https://www.practical-devsecops.com/top-container-security-tools/)

## How do you scan containers for vulnerabilities? 
**Tutorial: Scan a Docker container for vulnerabilities**
1. Create a new project.
2. Add a Dockerfile file to the project. ...
3. Create pipeline configuration for the new project to create a Docker image from the Dockerfile , build and push a Docker image to the container registry, and then scan the Docker image for vulnerabilities.
[More items...](https://docs.gitlab.com/ee/tutorials/container_scanning/)

## Which tool is used for container security?
**Anchore Engine**  
The open-source Anchore Engine is used to analyze container images and provide reporting on CVE-based security vulnerabilities. The Anchore Engine also assesses Docker images via custom rules to permit automated certification and validation.
[ **Container Security Tools: Top 7 Open-Source Options - Tigera**](https://www.tigera.io/learn/guides/container-security-best-practices/container-security-tools/)

# How to secure a container?
## How to secure docker containers?
**When using Docker containers, you should use the following practices to ensure maximum security.**
1. Avoid Root Permissions. ...
2. Use Secure Container Registries. ...
3. Limit Resource Usage. ...
4. Scan Your Images. ...
5. Build Your Networks and APIs for Security. ...
6. Docker Container Monitoring.
 [**Top 5 Docker Security Risks and Best Practices**](https://www.tigera.io/learn/guides/container-security-best-practices/docker-security/)






# Runc and runsc (gvisor) are not the same
[runc vs gvisor (runsc) vs rkt vs KataContainers ...](https://gist.github.com/miguelmota/8082507590d55c400c5dc520a43e14a1)


##### What is the difference between runC and ContainerD
What is the difference between runC and containerd?

![Docker vs Containerd vs RunC. Runc and Containerd are both ...](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTM480rBIxzAs-znjQiPFcwabnvJhOBkceo5FZjtjBc&s)

In other words, **runc provides the basic functionality for creating and running containers, while containerd provides a more complete environment for managing and orchestrating container workloads**. Containerd was originally developed by Docker, Inc. as a core component of the Docker platform
[**Docker vs Containerd vs RunC - Medium**](https://medium.com/@bibhup_mishra/docker-vs-containerd-vs-runc-c39ffd4156fb)

# Interesting reads/videos
- [Container Security, and the Importance of Secure Runtimes - The New Stack](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjX0cqf0OqDAxVpIUQIHWgTBkMQFnoECBEQAw&url=https%3A%2F%2Fthenewstack.io%2Fcontainer-security-and-the-importance-of-secure-runtimes%2F&usg=AOvVaw1-24nq4qzdtgArO1m7XuVn&opi=89978449)
- [gVisor, Kata Containers, Firecracker, Docker: Who is Who in the Container Space?](https://www.youtube.com/watch?v=HpAVlnl2Z9M&pp=ygUQZ1Zpc29yIGNvbnRhaW5lcg%3D%3D)
- [gVisor, The Future of Container Security - Andy Nguyen](https://www.youtube.com/watch?v=EcUs8Y0w0fQ&pp=ygUQZ1Zpc29yIGNvbnRhaW5lcg%3D%3D)
	- 6 months old, worth watching soon
- [Kubernetes Security - Container Runtime Sandboxes gVisor runsc/kata container - 15](https://www.youtube.com/watch?v=NZjAg7P-SDw&pp=ygUQZ1Zpc29yIGNvbnRhaW5lcg%3D%3D)
	- 1 year old, educational
- [Face off: VMs vs. Containers vs Firecracker](https://www.youtube.com/watch?v=pTQ_jVYhAoc&pp=ygUQZ1Zpc29yIGNvbnRhaW5lcg%3D%3D)
	- 8 months old
**Is this paper doing the project we had in mind???**
- [Blending Containers and Virtual Machines: A study of Firecracker and gVisor]([https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjAla-i0OqDAxVwPEQIHSZvBVoQFnoECAQQAw&url=https%3A%2F%2Fpages.cs.wisc.edu%2F~swift%2Fpapers%2Fvee20-isolation.pdf&usg=AOvVaw2ipsex_cG1D0dhngGu3s8K&opi=89978449](https://www.google.com/url?q=https://www.google.com/url?sa%3Dt%26rct%3Dj%26q%3D%26esrc%3Ds%26source%3Dweb%26cd%3D%26cad%3Drja%26uact%3D8%26ved%3D2ahUKEwjAla-i0OqDAxVwPEQIHSZvBVoQFnoECAQQAw%26url%3Dhttps%253A%252F%252Fpages.cs.wisc.edu%252F~swift%252Fpapers%252Fvee20-isolation.pdf%26usg%3DAOvVaw2ipsex_cG1D0dhngGu3s8K%26opi%3D89978449&sa=D&source=docs&ust=1705712062785727&usg=AOvVaw1LxsMXQLqSKqD7wRFiLHzD))

Datadog [report](https://www.datadoghq.com/container-report/) on containers.






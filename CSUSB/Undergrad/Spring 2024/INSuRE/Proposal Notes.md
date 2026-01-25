### To figure out
Why does this problem exist, and this is how we're going to approach it.
- Well, gVisor and Kata are making bold claims that they fixed this issue, what now?

*Understand that gVisor and firecracker use the Linux Kernel services differently.* 
- *How much does their use vary?* 
- *Performance costs?* 
- *Microbenchmarks targeting different kernel subsystems*
- Both softwares execute more kernel code than native Linux.
- Send the same code, but in different frequencies
- **Blending containers and virtual machines paper**

### Measurement ideas?
- Lets say gVisor is successful in blocking an attack. Note exactly where a normal container would have fallen short. 
	- Or maybe see if MicroVMs fell short. 
- Our project simply cannot be, will this technology work.
- Is gVisor "perfect"?
- Compare isolated sandboxed containers like kata and gVisor?
	- Time it takes to perform a container escape?
	- Time it takes to detect it?
	- If the extent of the damage difference
		- Risky, both claim it's none
	- Overhead for running this software?
	- Compare everything that someone has to do using this security method, compared to just regular Docker
- 



## Key terms
- Serverless computing
- Move functionality out of the host kernel, and into an isolated guest environment
- Strong isolation, high performance

#### Principles of serverless computing:
- Rapid scaling
- Efficient resource utilization
- Isolation for individual workloads

### gVisor
- User space kernel
- Handles syscalls between the container and the host kernel, limiting the type of syscalls that make it to the host kernel.
	- handles many system calls in a user-mode sentry process
- "**gVisor** is the **missing security layer** for running containers efficiently and securely."
- runs anywhere existing container tooling does. It enables cloud-native container security and portability
- Add defense-in-depth measures to your stack, bringing additional security to your infrastructure.
- Deliver runtime visibility that integrates with popular **threat detection tools** to quickly identify threats, generate alerts, and enforce policies.
- gVisor runs anywhere Linux does. It works on x86 and ARM, on VMs or bare-metal, and does not require virtualization support. **gVisor works well on all popular cloud providers**.
- gVisor **works with Docker, Kubernetes, and containerd**. Many popular applications and images are deployed in production environments on gVisor.

What are full fledged serverless platforms?

### FirecrackerD
- Lightweight VM with a complete guest kernel, but relies on the host OS to securely isolate the Firecracker hosting process. 
- AWS
- 

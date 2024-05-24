# Support for container runtimes?
Yes. Firecracker containerD. We can start containers within an indiviudal instance. Other companies are doing things with it, but not specifically container runtimes.
- [Spokeperson](https://www.youtube.com/watch?v=4d0NIfuFLXc&t=213s)  (15:35) said he hasn't seen it work with kubernetes


Example of Micro VM: Firecracker technology
lightweight virtualization
	Minimal vmm that uses KVM
Designed to priortize:
1. Secure
	1. Smaller attack surface
	2. Seccomp* ???
	3. cgroups/ns* ???
2. Fast 
	1. < 125 ms to launch* 
	2. Launch 100s per second/host*
3. Efficient /scalable
	1. < 5 MB overhead per vm

### What - devices? (Here's where micro comes in)
- Limited device emulation (a.k.a device model)
	- Does not try to emulate all devices
	- paravirtuzalization
	- Virtio devices 
	- devices emulated depend on implementation

- and this means:
	- "less hypervisor bloat"
	- Faster startup time
	- Reduced memory footprint
	- Smaller attack surface

### What - Boot / Volumes
- Volumes are rawfs files or block devices
	- Can be cumbersome to work with
	- Overlay filesystem & device mapper can help
	- Some projects use container images as volumes

- No BIOS, bootloader (depedning on implemetation_
	- Srtarts executing kernel directly
	- 


### What - API
- Most expose API
	- Per instance (usually via socket)
	- Configure to VM
	- Perform actions (i.e. start, stop, pause, snapshot)

- Metadata Services (depending on implementation)
	- Similar to the AWS instance metadata service
	- Useful for cloud-init, passing in data from host to guest (i.e secrets etc)

## Why should we care?

### Why - do more
![[Pasted image 20240119100750.png]]

## Why - Workload isolation

- **Virtual machines offer greater isolation vs containers**
- Workloads isolation may be required for
	- Regulatory 
	- Operational
	- Data Privacy
![[Pasted image 20240119101427.png]]
- Isolated a step in the pipeline through a VM
## Why - workload isolation

![[Pasted image 20240119101505.png]]

### Why - other exmaples
Other examples seen in the wild:
- Isolated build pipelines/runners
	- Github Runner in Firecracker
- Short lived testing/preview environments
- Short lived jobs


### How do we use it?
- 2 main implementations
	- Firecracker (FC) 
	- Cloud Hypervisor (CH)
- Both share similar heritage
	- Crosvm
	- Rust vmm crate
	- Diverged based on their use case
- There are others like QEMU microvm
	- But this came later
- X86 and ARM supported
- Instance per vm

### How - Firecracker
- Used & developed by AWS
- Primary use case is to support AWS internal customers
	- Lambda 
	- Fargate
	-  = Ephemeral Compute
- Smallest device model (no pci, no macvtap)
- Metadata service
- Cannot pause/resume/reboot
- **Increase security by using the Jailer** (but not required)
	- Cgroup
	- netns
	- seccomp filters
- Linux guests only

## How - Cloud Hypervisor 
(More features, more support)

- Developed by Intel, Alibaba and others
- More generalized & feature rich
- Larger device model compared to Firecracker
	- More virtio devices supported (e.g. vDPA)
	- PCI
	- SGX/TDX
	- macvtap
- No metadata service
	- Cloud init can still be done from a volume
- Linux and Windows guests


Overview
- Container escapes / What they are
- Our approach (Also our intended approach? with microVMs)
- Motivation 
- **Schedule** 
Methods and Procedures (process)
- Virtual box
- Ubuntu Server (Version?)
- Docker with Runc (Vulnerable version?)
- gVisor
Findings
- Success in getting the exploits to work
	- Go deep into the damage they would cause, **post screenshots**, or a video demonstration?
- gVisor works in Docker
- Exploits failed if we set the default runtime for Docker to runsc

Issues
- Issues with original project
	- **Bare metal server**
	- Confusion with microVM technologies (**We confused Firecracker-ContainerD, with ContainerD** *Ask Coulson*)
- gVisor had compatability issues with Intel Processors
- Integrating ConterinD with Gvisor (Shim repository is archived) 
Conclusions and Recommendations
- **Different CVEs that explore major risks for different core components of containers (Images, Registry, Orchestration, Containers, or Host OS)**
- **MicroVMs (Kata or Firecracker-ContainerD)**

Shims allow 





Overview
Methods and Procedures
- Method Characterization
- Deliverables/Schedule
- Limitations and Delimitations
Findings
- Host OS vs Image
- OS Security Posture
- Kernel Interactions
- Container Configuration
- Container Configuration options
- PID Limit Depreciation
- Secure Container YML Template
Issues
Conclusions and Recommendations
- Conclusions
- Future Work
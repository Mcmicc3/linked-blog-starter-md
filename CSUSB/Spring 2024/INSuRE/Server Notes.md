Overlay and underlay filesystem
- Interacts with the host kernel
- They're pretty cool


Christian is familiar with it.


Pick a service 

Awesome self hosted

Take a service, and learn how to put it in a docker container
https://github.com/awesome-selfhosted/awesome-selfhosted

WTF is a namespace (big part of docker)

Different runtime environments

compilation of containers.

Container runtimes where we can take tar files and run them as containers.


### Server rack
OS?

Limits of virtual machine?
- Is the biggest limit a virtual machine, or its resources?

Is it reliable 24/7?

Could we reserve 2 VS? one for microVM, and another for sandboxed containers?

UniFi OS

Proxmox???- vmware server

Docker is more bare metal


# Options for running environment


We have the option of running a command line server or gui server

1. Format the machine and install our own OS
2. Restricted network
	1. If we have any issues ask Hunter
3. Static IP
	1. Set it to DHCP, hunter reserved an IP address
Two types of storage - thumbstick 64 GB, used for the OS
Use the other drives on the server to store stuff, or install directly onto hard drives. 

Install OS to thumb drive preferably (64 GB), 


# Observations during installation
TrueNAS opened up

Booted into the USB drive, this started the installation process
The 

Should I change the boot order, or choose to boot straight into the USB everytime?

We installed the US onto the thumb drive, and will mnt drives as needed.


# Issues on VM

Trying to install gVisor on docker
- Doing this because it's easier than gVisor alone

It says I need to restart the docker [service](https://gvisor.dev/docs/user_guide/quick_start/docker/), However, I get the error that the docker service cannot be found. 
- `Failed to restart docker.service: Unit docker.service not found`

Found a [suggestion](https://askubuntu.com/questions/1427054/how-to-fix-the-unit-docker-service-could-not-be-found-error) to instead download docker using apt instead of the snap version 
- It's suggesting to uninstall all older verisions of Docker
- Could this lead to problems with our CVEs?
- Trying it

sudo snap remove docker
installing docker through [apt-get](https://docs.docker.com/engine/install/ubuntu/)
- Successfully installer Docker version 24.0.8
- Patch for leaky vessels is found on 24.0.9


### Problem running hello-world with runsc
I consistantly ran into this issue. I tried upgrading to the latest version of runsc and continued running into this error.
`root@insure:/home/insure# docker run --runtime=runsc --rm hello-world
`docker: Error response from daemon: failed to create task for container: failed to create shim task: OCI runtime create failed: creating container: cannot create sandbox: cannot read client sync file: waiting for sandbox to start: EOF: unknown.`

Versions of runsc and docker
`root@insure:/home/insure# runsc --version`
`runsc version release-20240212.0
`spec: 1.1.0-rc.1

`root@insure:/home/insure# docker -v
`Docker version 25.0.3, build 4debf41
`root@insure:/home/insure#

Resources: 2 GBs of RAM, 50 GB of storage, and 4 processors
It works just fine on Alexs terminal, and  we have the same versions, ,and he's using less resources.

Reinstalling runsc and gVisor. 

#### Continuous problems getting runsc to work
I tried starting from scratch, didn't install the docker snap in, followed the same instructions, same error. I've consistently been working with the latest version of docker. I tried an older version of docker, the newest version of docker. Tried different SSIDs. Not seeing anything related to this issue on the [github](https://github.com/google/gvisor/issues).

Trying the [build](https://github.com/google/gvisor) section on github
- Had to run sudo apt-get install make
Getting errors with this command: 
`make copy TARGETS=runsc DESTINATION=bin/`

Turns out that gVisor has a [makefile](https://github.com/google/gvisor/blob/master/Makefile), This could explain why the copy command isn't working. 


#### Matching Alex's resources

Alex claims he got it to run on 2GB of memory, One processor, and 25 GB of storage, and he has gVisor working.

I just tried the same configurations, and I'm getting Kernel Panic 
![[Trash/SYNC/Images/Pasted image 20240224184126.png]]

Now that I gave it 2 more GBs of storage, and another CPU processor, it's working fine

![[Trash/SYNC/Images/Pasted image 20240224184333.png]]

##### Version of Docker I'm trying to install
VERSION_STRING=5:24.0.8-1~ubuntu.22.04~jammy

 sudo apt-get install docker-ce=$VERSION_STRING docker-ce-cli=$VERSION_STRING containerd.io docker-buildx-plugin docker-compose-plugin

I tried giving 8 GB of memory, 4 processors, same goddam error.

I'm gonna try downloading the **latest version** of docker....

insure@insure:~$ docker run --runtime=runsc --rm hello-world
docker: permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/create": dial unix /var/run/docker.sock: connect: permission denied.
See 'docker run --help'.
insure@insure:~$ sudo docker run --runtime=runsc --rm hello-world
docker: Error response from daemon: failed to create task for container: failed to create shim task: OCI runtime create failed: creating container: cannot create sandbox: cannot read client sync file: waiting for sandbox to start: EOF: unknown.
insure@insure:~$


![[Trash/SYNC/Images/Pasted image 20240224200611.png]]
Tried manually installing it....got a new error

#### [](https://github.com/glotcode/docker-run/blob/main/docs/install/ubuntu-20.10-gvisor.md#set-runsc-as-the-default-runtime)Set runsc as the default runtime
Editing the daemon.json directly. 


Add a `default-runtime` field to `/etc/docker/daemon.json`. The file should look something like this:

```js
{
    ...
    "default-runtime": "runsc",
    "runtimes": {
        "runsc": {
            "path": "/usr/bin/runsc"
        }
    }
}
```

**Solution hasn't been edited in 4 years**

#### Aldo Suggests to install Docker before gVisor
run systemctl as soon as it finishes installing, just to confirm everything is running fine. 
- Confirmed systemctl works fine

Same error

docker: Error response from daemon: failed to create task for container: failed to create shim task: OCI runtime create failed: creating container: cannot create sandbox: cannot read client sync file: waiting for sandbox to start: EOF: unknown.


# Editing the daemon.json file to configure shim
Used configuration suggestions from Docker


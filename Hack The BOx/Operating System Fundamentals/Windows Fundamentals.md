# Introduction to Windows

| Operating System Names | Version Number |
| ---- | ---- |
| Windows NT 4 | 4.0 |
| Windows 2000 | 5.0 |
| Windows XP | 5.1 |
| Windows Server 2003, 2003 R2 | 5.2 |
| Windows Vista, Server 2008 | 6.0 |
| Windows 7, Server 2008 R2 | 6.1 |
| Windows 8, Server 2012 | 6.2 |
| Windows 8.1, Server 2012 R2 | 6.3 |
| Windows 10, Server 2016, Server 2019 | 10.0 |
We can use the [Get-WmiObject](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1) [cmdlet](https://docs.microsoft.com/en-us/powershell/scripting/developer/cmdlet/cmdlet-overview?view=powershell-7) to find information about the operating system. This cmdlet can be used to get instances of WMI classes or information about available WMI classes. There are a variety of ways to find the version and build number of our system. We can easily obtain this information using the `win32_OperatingSystem` class, which shows that we are on a Windows 10 host, build number 19041.

```powershell-session
PS C:\htb> Get-WmiObject -Class win32_OperatingSystem | select Version,BuildNumber

Version    BuildNumber
-------    -----------
10.0.19041 19041
```

Some other useful classes that can be used with `Get-WmiObject` are `Win32_Process` to get a process listing, `Win32_Service` to get a listing of services, and `Win32_Bios` to get [Basic Input/Output System](https://en.wikipedia.org/wiki/BIOS) (`BIOS`) information. The BIOS is firmware installed on a computer's motherboard that controls the computer's essential functions, such as power management, input/output interfaces, and system configuration. We can use the `ComputerName` parameter to get information about remote computers. `Get-WmiObject` can be used to start and stop services on local and remote computers, and more.

### Remote Access
Some of the most common remote access technologies include but aren't limited to:

- Virtual Private Networks (VPN)
- Secure Shell (SSH)
- File Transfer Protocol (FTP)
- Virtual Network Computing (VNC)
- Windows Remote Management (or PowerShell Remoting) (WinRM)
- Remote Desktop Protocol (RDP)

We can use RDP to connect to a Windows target from an attack host running Linux or Windows. If we are connecting to a Windows target from a Windows host, we can use the built-in RDP client application called `Remote Desktop Connection` ([mstsc.exe](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/mstsc)). 

Remote Desktop Connection also allows us to save connection profiles. This is a common habit among IT admins because it makes connecting to remote systems more convenient.
As pentesters, we can benefit from looking for these saved Remote Desktop Files (`.rdp`) while on an engagement.

### Using xfreerdp
From a Linux-based attack host we can use a tool called [xfreerdp](https://linux.die.net/man/1/xfreerdp) to remotely access Windows targets. You will notice that we use xfreerdp across multiple modules because of its ease of use, feature set, command line utility, and efficiency. Check out the clip below to see basic usage from Pwnbox:

```shell-session
Fr1zzleFry@htb[/htb]$ xfreerdp /v:<targetIp> /u:htb-student /p:Password
```

# Operating System Structure

The directory structure of the boot partition is as follows:

| Directory | Function |
| ---- | ---- |
| Perflogs | Can hold Windows performance logs but is empty by default. |
| Program Files | On 32-bit systems, all 16-bit and 32-bit programs are installed here. On 64-bit systems, only 64-bit programs are installed here. |
| Program Files (x86) | 32-bit and 16-bit programs are installed here on 64-bit editions of Windows. |
| ProgramData | This is a hidden folder that contains data that is essential for certain installed programs to run. This data is accessible by the program no matter what user is running it. |
| Users | This folder contains user profiles for each user that logs onto the system and contains the two folders Public and Default. |
| Default | This is the default user profile template for all created users. Whenever a new user is added to the system, their profile is based on the Default profile. |
| Public | This folder is intended for computer users to share files and is accessible to all users by default. This folder is shared over the network by default but requires a valid network account to access. |
| AppData | Per user application data and settings are stored in a hidden user subfolder (i.e., cliff.moore\AppData). Each of these folders contains three subfolders. The Roaming folder contains machine-independent data that should follow the user's profile, such as custom dictionaries. The Local folder is specific to the computer itself and is never synchronized across the network. LocalLow is similar to the Local folder, but it has a lower data integrity level. Therefore it can be used, for example, by a web browser set to protected or safe mode. |
| Windows | The majority of the files required for the Windows operating system are contained here. |
| System, System32, SysWOW64 | Contains all DLLs required for the core features of Windows and the Windows API. The operating system searches these folders any time a program asks to load a DLL without specifying an absolute path. |
| WinSxS | The Windows Component Store contains a copy of all Windows components, updates, and service packs. |

### Exploring Directories Using Command Line

We can explore the file system using the [dir](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/dir) command.
The [tree](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/tree) utility is useful for graphically displaying the directory structure of a path or disk.

```cmd-session
C:\htb> dir c:\ /a
 Volume in drive C has no label.
 Volume Serial Number is F416-77BE

 Directory of c:\

08/16/2020  10:33 AM    <DIR>          $Recycle.Bin
06/25/2020  06:25 PM    <DIR>          $WinREAgent
07/02/2020  12:55 PM             1,024 AMTAG.BIN
```

```cmd-session
C:\htb> tree "c:\Program Files (x86)\VMware"
Folder PATH listing
Volume serial number is F416-77BE
C:\PROGRAM FILES (X86)\VMWARE
├───VMware VIX
│   ├───doc
│   │   ├───errors
│   │   ├───features
<SNIP>
```


# File System
FAT32 (File Allocation Table) is widely used across many types of storage devices such as USB memory sticks and SD cards but can also be used to format hard drives. The "32" in the name refers to the fact that FAT32 uses 32 bits of data for identifying data clusters on a storage device.

**`Pros of FAT32:`**

- Device compatibility - it can be used on computers, digital cameras, gaming consoles, smartphones, tablets, and more.
- Operating system cross-compatibility - It works on all Windows operating systems starting from Windows 95 and is also supported by MacOS and Linux.

NTFS (New Technology File System) is the default Windows file system since Windows NT 3.1. In addition to making up for the shortcomings of FAT32, NTFS also has better support for metadata and better performance due to improved data structuring.

**`Cons of NTFS:`**

- Most mobile devices do not support NTFS natively.
- Older media devices such as TVs and digital cameras do not offer support for NTFS storage devices.

### Permissions

The NTFS file system has many basic and advanced permissions. Some of the key permission types are:

|Permission Type|Description|
|---|---|
|Full Control|Allows reading, writing, changing, deleting of files/folders.|
|Modify|Allows reading, writing, and deleting of files/folders.|
|List Folder Contents|Allows for viewing and listing folders and subfolders as well as executing files. Folders only inherit this permission.|
|Read and Execute|Allows for viewing and listing files and subfolders as well as executing files. Files and folders inherit this permission.|
|Write|Allows for adding files to folders and subfolders and writing to a file.|
|Read|Allows for viewing and listing of folders and subfolders and viewing a file's contents.|
|Traverse Folder|This allows or denies the ability to move through folders to reach other files or folders. For example, a user may not have permission to list the directory contents or view files in the documents or web apps directory in this example c:\users\bsmith\documents\webapps\backups\backup_02042020.zip but with Traverse Folder permissions applied, they can access the backup archive.|
Set permissions to parent folders
### Integrity Control Access Control List (icacls)
NTFS permissions on files and folders in Windows can be managed using the File Explorer GUI under the security tab. Apart from the GUI, we can also achieve a fine level of granularity over NTFS file permissions in Windows from the command line using the icacls utility.

We can list out the NTFS permissions on a specific directory by running either `icacls` from within the working directory or `icacls C:\Windows` against a directory not currently in.

```cmd-session
C:\htb> icacls c:\windows
c:\windows NT SERVICE\TrustedInstaller:(F)
           NT SERVICE\TrustedInstaller:(CI)(IO)(F)
           NT AUTHORITY\SYSTEM:(M)
           NT AUTHORITY\SYSTEM:(OI)(CI)(IO)(F)
```

The resource access level is listed after each user in the output. The possible inheritance settings are:

- `(CI)`: container inherit
- `(OI)`: object inherit
- `(IO)`: inherit only
- `(NP)`: do not propagate inherit
- `(I)`: permission inherited from parent container

Basic access permissions are as follows:

- `F` : full access
- `D` :  delete access
- `N` :  no access
- `M` :  modify access
- `RX` :  read and execute access
- `R` :  read-only access
- `W` :  write-only access

We can add and remove permissions via the command line using `icacls`. Here we are executing `icacls` in the context of a local administrator account showing the `C:\users` directory where the `joe` user does not have any write permissions.

```cmd-session
C:\htb> icacls c:\Users
c:\Users NT AUTHORITY\SYSTEM:(OI)(CI)(F)
         BUILTIN\Administrators:(OI)(CI)(F)
         BUILTIN\Users:(RX)
         BUILTIN\Users:(OI)(CI)(IO)(GR,GE)
         Everyone:(RX)
         Everyone:(OI)(CI)(IO)(GR,GE)

Successfully processed 1 files; Failed processing 0 files
```

Using the command `icacls c:\users /grant joe:f` we can grant the joe user full control over the directory, but given that `(oi)` and `(ci)` were not included in the command, the joe user will only have rights over the `c:\users` folder but not over the user subdirectories and files contained within them.

```cmd-session
C:\htb> icacls c:\users /grant joe:f
processed file: c:\users
Successfully processed 1 files; Failed processing 0 files
```

```cmd-session
C:\htb> >icacls c:\users
c:\users WS01\joe:(F)
         NT AUTHORITY\SYSTEM:(OI)(CI)(F)
         BUILTIN\Administrators:(OI)(CI)(F)
         BUILTIN\Users:(RX)
         BUILTIN\Users:(OI)(CI)(IO)(GR,GE)
         Everyone:(RX)
         Everyone:(OI)(CI)(IO)(GR,GE)

Successfully processed 1 files; Failed processing 0 files
```

These permissions can be revoked using the command `icacls c:\users /remove joe`.

`icacls` is very powerful and can be used in a domain setting to give certain users or groups specific permissions over a file or folder, explicitly deny access, enable or disable inheritance permissions, and change directory/file ownership.

# NTFS vs. Share Permissions
The `Server Message Block protocol` (`SMB`) is used in Windows to connect shared resources like files and printers. It is used in large, medium, and small enterprise environments. See the image below to visualize this concept:

NTFS permissions and share permissions are often understood to be the same. Please know that `they are not the same `but often apply to the same shared resource. Let’s take a look at the individual permissions that can be set to secure/grant objects access to a network share hosted on a Windows OS running the NTFS file system.

### Share permissions

|Permission|Description|
|---|---|
|`Full Control`|Users are permitted to perform all actions given by Change and Read permissions as well as change permissions for NTFS files and subfolders|
|`Change`|Users are permitted to read, edit, delete and add files and subfolders|
|`Read`|Users are allowed to view file & subfolder contents|
### NTFS Basic permissions

|Permission|Description|
|---|---|
|`Full Control`|Users are permitted to add, edit, move, delete files & folders as well as change NTFS permissions that apply to all allowed folders|
|`Modify`|Users are permitted or denied permissions to view and modify files and folders. This includes adding or deleting files|
|`Read & Execute`|Users are permitted or denied permissions to read the contents of files and execute programs|
|`List folder contents`|Users are permitted or denied permissions to view a listing of files and subfolders|
|`Read`|Users are permitted or denied permissions to read the contents of files|
|`Write`|Users are permitted or denied permissions to write changes to a file and add new files to a folder|
|`Special Permissions`|A variety of advanced permissions options|
### NTFS special permissions

|Permission|Description|
|---|---|
|`Full control`|Users are permitted or denied permissions to add, edit, move, delete files & folders as well as change NTFS permissions that apply to all permitted folders|
|`Traverse folder / execute file`|Users are permitted or denied permissions to access a subfolder within a directory structure even if the user is denied access to contents at the parent folder level. Users may also be permitted or denied permissions to execute programs|
|`List folder/read data`|Users are permitted or denied permissions to view files and folders contained in the parent folder. Users can also be permitted to open and view files|
|`Read attributes`|Users are permitted or denied permissions to view basic attributes of a file or folder. Examples of basic attributes: system, archive, read-only, and hidden|
|`Read extended attributes`|Users are permitted or denied permissions to view extended attributes of a file or folder. Attributes differ depending on the program|
|`Create files/write data`|Users are permitted or denied permissions to create files within a folder and make changes to a file|
|`Create folders/append data`|Users are permitted or denied permissions to create subfolders within a folder. Data can be added to files but pre-existing content cannot be overwritten|
|`Write attributes`|Users are permitted or denied to change file attributes. This permission does not grant access to creating files or folders|
|`Write extended attributes`|Users are permitted or denied permissions to change extended attributes on a file or folder. Attributes differ depending on the program|
|`Delete subfolders and files`|Users are permitted or denied permissions to delete subfolders and files. Parent folders will not be deleted|
|`Delete`|Users are permitted or denied permissions to delete parent folders, subfolders and files.|
|`Read permissions`|Users are permitted or denied permissions to read permissions of a folder|
|`Change permissions`|Users are permitted or denied permissions to change permissions of a file or folder|
|`Take ownership`|Users are permitted or denied permission to take ownership of a file or folder. The owner of a file has full permissions to change any permissions|
Keep in mind that NTFS permissions apply to the system where the folder and files are hosted. Folders created in NTFS inherit permissions from parent folders by default. It is possible to disable inheritance to set custom permissions on parent and subfolders, as we will do later in this module. The share permissions apply when the folder is being accessed through SMB, typically from a different system over the network. This means someone logged in locally to the machine or via RDP can access the shared folder and files by simply navigating to the location on the file system and only need to consider NTFS permissions. The permissions at the NTFS level provide administrators much more granular control over what users can do within a folder or file.

## Creating a Network Share
We are going to use the `Advanced Sharing` option to configure our share.

![[Pasted image 20231226192426.png]]Similar to NTFS permissions, there is an `access control list` (`ACL`) for shared resources. We can consider this the SMB permissions list. Keep in mind that with shared resources, both the SMB and NTFS permissions lists apply to every resource that gets shared in Windows. The ACL contains `access control entries` (`ACEs`). Typically these ACEs are made up of `users` & `groups` (also called security principals) as they are a suitable mechanism for managing and tracking access to shared resources.

![[Pasted image 20231226192630.png]]
For now, we are going to apply these settings to test the effect of this ACL and the permissions applied as-is. We will test connectivity from the Pwnbox by opening terminal and using `smbclient`.

#### Using smbclient to Connect to the Share

```shell-session
Fr1zzleFry@htb[/htb]$ smbclient -L IPaddressOfTarget -U htb-student
Enter WORKGROUP\htb-student's password: 

	Sharename       Type      Comment
	---------       ----      -------
	ADMIN$          Disk      Remote Admin
	C$              Disk      Default share
	Company Data    Disk      
	IPC$            IPC       Remote IPC
```

## Windows Defender Firewall Considerations

It is the Windows Defender Firewall that could potentially be blocking access to the SMB share. Since we are connecting from a Linux-based system the firewall has blocked access from any device that is not joined to the same `workgroup`. It is also important to note that when a Windows system is part of a workgroup, all `netlogon` requests are authenticated against that particular Windows system's `SAM` database. When a Windows system is joined to a Windows Domain environment, all netlogon requests are authenticated against `Active Directory`. The primary difference between a workgroup and a Windows Domain in terms of authentication, is with a workgroup the local SAM database is used and in a Windows Domain a centralized network-based database (Active Directory) is used. We must know this information when attempting to logon & authenticate with a Windows system. Consider where the htb-student account is hosted to properly connect to the target.

Windows Defender Firewall Profiles:

- `Public`
- `Private`
- `Domain`

Once the proper `inbound` firewall rules are enabled we will successfully connect to the share. Keep in mind that we can only connect to the share because the user account we are using (`htb-student`) is in the `Everyone group`. Recall that we left the specific share permissions for the Everyone group set to Read, which quite literally means we will only be able to Read files on this share. Once a connection is established with a share, we can create a `mount point` from our Pwnbox to the Windows 10 target box's file system. This is where we must also consider that NTFS permissions apply alongside share permissions. Recall that NTFS is the default file system in Windows. Lets jump back to our xfreerdp session with our Windows 10 target box and take a look at the NTFS permissions on the Company Data folder.

Now lets give the Everyone group `Full control` at the share level and test the impact of the change by trying to create a mount point to the share from the Desktop of our Pwnbox

Mounting to the Share

```shell-session
Fr1zzleFry@htb[/htb]$ sudo mount -t cifs -o username=htb-student,password=Academy_WinFun! //ipaddoftarget/"Company Data" /home/user/Desktop/
```

If this command is not working check the syntax. If the syntax is correct yet the command is still not working, `cifs-utils` may need to be installed. This can be done with the following command:

#### Installing CIFS Utilities

```shell-session
Fr1zzleFry@htb[/htb]$ sudo apt-get install cifs-utils
```

Once we have successfully created the mount point on the Desktop on our Pwnbox, we should look at a couple of tools built-in to Windows that will allow us to track and monitor what we have done.

The `net share` command allows us to view all the shared folders on the system. Notice the share we created and also the C:\ drive.

- Computer Management
- Event Viewer

# Windows Services & Processes 

Applications can also be created to install as a service, such as a network monitoring application installed on a server. Services on Windows are responsible for many functions within the Windows operating system, such as networking functions, performing system diagnostics, managing user credentials, controlling Windows updates, and more.

Windows services are managed via the Service Control Manager (SCM) system, accessible via the `services.msc` MMC add-in.

This add-in provides a GUI interface for interacting with and managing services and displays information about each installed service. This information includes the service Name, Description, Status, Startup Type, and the user that the service runs under.

It is also possible to query and manage services via the command line using `sc.exe` using [PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-7) cmdlets such as `Get-Service`.

```powershell-session
PS C:\htb> Get-Service | ? {$_.Status -eq "Running"} | select -First 2 |fl


Name                : AdobeARMservice
DisplayName         : Adobe Acrobat Update Service
```

Service statuses can appear as Running, Stopped, or Paused, and they can be set to start manually, automatically, or on a delay at system boot. Services can also be shown in the state of Starting or Stopping if some action has triggered them to either start or stop. Windows has three categories of services: Local Services, Network Services, and System Services. Services can usually only be created, modified, and deleted by users with administrative privileges. Misconfigurations around service permissions are a common privilege escalation vector on Windows systems.

In Windows, we have some [critical system services](https://docs.microsoft.com/en-us/windows/win32/rstmgr/critical-system-services) that cannot be stopped and restarted without a system restart. If we update any file or resource in use by one of these services, we must restart the system.

## Processes

Processes run in the background on Windows systems. They either run automatically as part of the Windows operating system or are started by other installed applications.

Processes associated with installed applications can often be terminated without causing a severe impact on the operating system. Certain processes are critical and, if terminated, will stop certain components of the operating system from running properly.

## Local Security Authority Subsystem Service (LSASS)

`lsass.exe` is the process that is responsible for enforcing the security policy on Windows systems. When a user attempts to log on to the system, this process verifies their log on attempt and creates access tokens based on the user's permission levels. LSASS is also responsible for user account password changes. All events associated with this process (logon/logoff attempts, etc.) are logged within the Windows Security Log. LSASS is an extremely high-value target as several tools exist to extract both cleartext and hashed credentials stored in memory by this process.

## Sysinternals Tools

The [SysInternals Tools suite](https://docs.microsoft.com/en-us/sysinternals) is a set of portable Windows applications that can be used to administer Windows systems (for the most part without requiring installation). The tools can be either downloaded from the Microsoft website or by loading them directly from an internet-accessible file share by typing `\\live.sysinternals.com\tools` into a Windows Explorer window.

For example, we can run procdump.exe directly from this share without downloading it directly to disk.

```cmd-session
C:\htb> \\live.sysinternals.com\tools\procdump.exe -accepteula
```

The suite includes tools such as `Process Explorer`, an enhanced version of `Task Manager`, and `Process Monitor`, which can be used to monitor file system, registry, and network activity related to any process running on the system. Some additional tools are TCPView, which is used to monitor internet activity, and PSExec, which can be used to manage/connect to systems via the SMB protocol remotely.

These tools can be useful for penetration testers to, for example, discover interesting processes and possible privilege escalation paths as well as for lateral movement.

## Task Manager
| Tab | Description |
| ---- | ---- |
| Processes tab | Shows a list of running applications and background processes along with the CPU, memory, disk, network, and power usage for each. |
| Performance tab | Shows graphs and data such as CPU utilization, system uptime, memory usage, disk and, networking, and GPU usage. We can also open the `Resource Monitor`, which gives us a much more in-depth view of the current CPU, Memory, Disk, and Network resource usage. |
| App history tab | Shows resource usage for the current user account for each application for a period of time. |
| Startup tab | Shows which applications are configured to start at boot as well as the impact on the startup process. |
| Users tab | Shows logged in users and the processes/resource usage associated with their session. |
| Details tab | Shows the name, process ID (PID), status, associated username, CPU, and memory usage for each running application. |
| Services tab | Shows the name, PID, description, and status of each installed service. The Services add-in can be accessed from this tab as well. |
## Process Explorer

[Process Explorer](https://docs.microsoft.com/en-us/sysinternals/downloads/process-explorer) is a part of the Sysinternals tool suite. This tool can show which handles and DLL processes are loaded when a program runs. Process Explorer shows a list of currently running processes, and from there, we can see what handles the process has selected in one view or the DLLs and memory-swapped files that have been loaded in another view. We can also search within the tool to show which processes tie back to a specific handle or DLL. The tool can also be used to analyze parent-child process relationships to see what child processes are spawned by an application and help troubleshoot any issues such as orphaned processed that can be left behind when a process is terminated.

**Questions**
Identify one of the non-standard update services running on the host. Submit the full name of the service executable (not the DisplayName) as your answer.
```cmd-session
htb-student> Get-Service | Where-Object {$_.Name -like "*reader*"} |fl

**Name: FoxitReaderUpdateService.exe**
```

# Service Permissions
Recall that services allow for the management of long-running processes and are a critical part of Windows operating systems. Sysadmins often overlook them as potential threat vectors that can be used to load malicious DLLs, execute applications without access to an admin account, escalate privileges and even maintain persistence. These threat vectors in Windows services often come into existence through service permissions misconfigurations put in place by 3rd party software and easy to make mistakes by admins during install processes.

The first step in realizing the importance of service permissions is simply understanding that they exist and being mindful of them. On server operating systems, critical network services like DHCP and Active Directory Domain Services commonly get installed using the account assigned to the admin performing the install. Part of the install process includes assigning a specific service to run using the credentials and privileges of a designated user, which by default is set within the currently logged-on user context.

For example, if we are logged on as Bob on a server during DHCP install, then that service will be configured to run as Bob unless specified otherwise. What bad things could come of this? Well, what if Bob leaves the organization or gets fired? The typical business practice would be to disable Bob’s account as part of his exit process. In this case, what would happen to DHCP and other services running using Bob’s account? Those services would fail to start. DHCP or Dynamic Host Configuration Protocol is responsible for leasing IP addresses to computers on the network. If this service stops on a Windows DHCP server, clients requesting an IP address will not receive one. This means a service misconfiguration could lead to downtime and loss of productivity. It is highly recommended to create an individual user account to run critical network services. These are referred to as `service accounts.

We should also be mindful of service permissions and the permissions of the directories they execute from because it is possible to replace the path to an executable with a malicious DLL or executable file.

## Examining Services using services.msc

As discussed in the processes and services section, we can use `services.msc` to view and manage just about every detail regarding all services. Let's take a closer look at the service associated with `Windows Update` (`wuauserv`).

Make a note of the different properties available for viewing and configuration. Knowing the service name is especially useful when using command-line tools to examine and manage services. Path to the executable is the full path to the program and command to execute when the service starts. If the NTFS permissions of the destination directory are configured with weak permissions, an attacker could replace the original executable with one created for malicious purposes. We discuss NTFS permissions more in the NTFS vs. Share permissions section of this module.

Most services run with LocalSystem privileges by default which is the highest level of access allowed on an individual Windows OS. Not all applications need Local System account-level permissions, so it is beneficial to perform research on a case-by-case basis when considering installing new applications in a Windows environment. It is a good practice to identify applications that can run with the least privileges possible to align with the principle of least privilege.

Notable built-in service accounts in Windows:

- LocalService
- NetworkService
- LocalSystem

Note: We can also create new accounts and use them for the sole purpose of running a service.

![[Pasted image 20231226220103.png]]
The recovery tab allows steps to be configured should a service fail. Notice how this service can be set to run a program after the first failure. This is yet another vector that an attacker could use to run malicious programs by utilizing a legitimate service.

## Examining services using sc

Sc can also be used to configure and manage services. Let's experiment with a few commands.

```cmd-session
C:\Users\htb-student>sc qc wuauserv
```

The `sc qc` command is used to query the service. This is where knowing the names of services can come in handy. If we wanted to query a service on a device over the network, we could specify the hostname or IP address immediately after `sc`.

```cmd-session
C:\Users\htb-student>sc //hostname or ip of box query ServiceName

```

We can also use sc to start and stop services.

```cmd-session
C:\Users\htb-student> sc stop wuauserv

[SC] OpenService FAILED 5:

Access is denied.
```

Notice how we are denied access from performing this action without running it within an administrative context. If we run a command prompt with `elevated privileges`, we will be permitted to complete this action.

```cmd-session
C:\WINDOWS\system32> sc config wuauserv binPath=C:\Winbows\Perfectlylegitprogram.exe

[SC] ChangeServiceConfig SUCCESS
```

If we were investigating a situation where we suspected that the system had malware, sc would give us the ability to quickly search and analyze commonly targeted services and newly created services. It’s also much more script-friendly than utilizing GUI tools like `services.msc`.

Another helpful way we can examine service permissions using `sc` is through the `sdshow` command.

```cmd-session
C:\WINDOWS\system32> sc sdshow wuauserv

D:(A;;CCLCSWRPLORC;;;AU)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;SY)S:(AU;FA;CCDCLCSWRPWPDTLOSDRCWDWO;;;WD)
```

At an initial glance, the output looks crazy. It almost seems that we have done something wrong in our command, but there is a meaning to this madness. Every named object in Windows is a [securable object](https://docs.microsoft.com/en-us/windows/win32/secauthz/securable-objects), and even some unnamed objects are securable. If it's securable in a Windows OS, it will have a [security descriptor](https://docs.microsoft.com/en-us/windows/win32/secauthz/security-descriptors). Security descriptors identify the object’s owner and a primary group containing a `Discretionary Access Control List` (`DACL`) and a `System Access Control List` (`SACL`).

Generally, a DACL is used for controlling access to an object, and a SACL is used to account for and log access attempts. This section will examine the DACL, but the same concepts would apply to a SACL.

```
D:(A;;CCLCSWRPLORC;;;AU)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;SY)
```

This amalgamation of characters crunched together and delimited by opened and closed parentheses is in a format known as the `Security Descriptor Definition Language` (`SDDL`).

We may be tempted to read from left to right because that is how the English language is typically written, but it can be much different when interacting with computers. Read the entire security descriptor for the `Windows Update` (`wuauserv`) service in this order starting with the first letter and set of parentheses:

`D: (A;;CCLCSWRPLORC;;;AU)`

1. D: - the proceeding characters are DACL permissions
2. AU: - defines the security principal Authenticated Users
3. A;; - access is allowed
4. CC - SERVICE_QUERY_CONFIG is the full name, and it is a query to the service control manager (SCM) for the service configuration
5. LC - SERVICE_QUERY_STATUS is the full name, and it is a query to the service control manager (SCM) for the current status of the service
6. SW - SERVICE_ENUMERATE_DEPENDENTS is the full name, and it will enumerate a list of dependent services
7. RP - SERVICE_START is the full name, and it will start the service
8. LO - SERVICE_INTERROGATE is the full name, and it will query the service for its current status
9. RC - READ_CONTROL is the full name, and it will query the security descriptor of the service

As we read the security descriptor, it can be easy to get lost in the seemingly random order of characters, but recall that we are essentially viewing access control entries in an access control list. Each set of 2 characters in between the semi-colons represents actions allowed to be performed by a specific user or group.

`;;CCLCSWRPLORC;;;`

After the last set of semi-colons, the characters specify the security principal (User and/or Group) that is permitted to perform those actions.

`;;;AU`

The character immediately after the opening parentheses and before the first set of semi-colons defines whether the actions are Allowed or Denied.

`A;;`

This entire security descriptor associated with the `Windows Update` (`wuauserv`) service has three sets of access control entries because there are three different security principals. Each security principal has specific permissions applied.

## Examine service permissions using PowerShell

Using the `Get-Acl` PowerShell cmdlet, we can examine service permissions by targeting the path of a specific service in the registry.

```powershell-session
PS C:\Users\htb-student> Get-ACL -Path HKLM:\System\CurrentControlSet\Services\wuauserv | Format-List
```

Notice how this command returns specific account permissions in an easy-to-read format and in SDDL. Also, the SID that represents each security principal (User and/or Group) is present in the SDDL. This is something we do not get when running `sc` from the command prompt.

Knowing how to interact with services and their associated permissions from the command line makes it easier to script out these tasks. While it is good to know how to perform these tasks from the GUI, it does not scale well as we start getting into larger network environments and Domains.

# Windows Session
#### Interactive

An interactive, or local logon session, is initiated by a user authenticating to a local or domain system by entering their credentials. An interactive logon can be initiated by logging directly into the system, by requesting a secondary logon session using the `runas` command via the command line, or through a Remote Desktop connection.

#### Non-interactive

Non-interactive accounts in Windows differ from standard user accounts as they do not require login credentials. There are 3 types of non-interactive accounts: the Local System Account, Local Service Account, and the Network Service Account. Non-interactive accounts are generally used by the Windows operating system to automatically start services and applications without requiring user interaction. These accounts have no password associated with them and are usually used to start services when the system boots or to run scheduled tasks.

There are differences between the three types of accounts:

|Account|Description|
|---|---|
|Local System Account|Also known as the `NT AUTHORITY\SYSTEM` account, this is the most powerful account in Windows systems. It is used for a variety of OS-related tasks, such as starting Windows services. This account is more powerful than accounts in the local administrators group.|
|Local Service Account|Known as the `NT AUTHORITY\LocalService` account, this is a less privileged version of the SYSTEM account and has similar privileges to a local user account. It is granted limited functionality and can start some services.|
|Network Service Account|This is known as the `NT AUTHORITY\NetworkService` account and is similar to a standard domain user account. It has similar privileges to the Local Service Account on the local machine. It can establish authenticated sessions for certain network services.|

# Interacting with the Windows Operating System

The help command works the same as `man` in Linux.
`C:\htb> help ipconfig`

Note that certain commands have their own help menus, which can be accessed by typing `<command> /?`. For example, information about the `ipconfig` command can be seen below.

Graphical User Interface

```cmd-session
C:\htb> ipconfig /?
```

## Cmdlets

PowerShell utilizes [cmdlets](https://docs.microsoft.com/en-us/powershell/scripting/developer/cmdlet/cmdlet-overview?view=powershell-7), which are small single-function tools built into the shell. There are more than 100 core cmdlets, and many additional ones have been written, or we can author our own to perform more complex tasks. PowerShell also supports both simple and complex scripts used for system administration tasks, automation, and more.

Cmdlets are in the form of `Verb-Noun`. For example, the command `Get-ChildItem` can be used to list our current directory. Cmdlets also take arguments or flags. We can type `Get-ChildItem -` and hit the tab key to iterate through the arguments. A command such as `Get-ChildItem -Recurse` will show us the contents of our current working directory and all subdirectories. Another example would be `Get-ChildItem -Path C:\Users\Administrator\Documents` to get the contents of another directory. Finally, we can combine arguments such as this to list all subdirectories' contents within another directory recursively: `Get-ChildItem -Path C:\Users\Administrator\Downloads -Recurse`.

---

## Aliases

Many cmdlets in PowerShell also have aliases. For example, the aliases for the cmdlet `Set-Location`, to change directories, is either `cd` or `sl`. Meanwhile, the aliases for `Get-ChildItem` are `ls` and `gci`. We can view all available aliases by typing `Get-Alias`.

Graphical User Interface

```powershell-session
PS C:\htb> get-alias

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
```

We can also set up our own aliases with `New-Alias` and get the alias for any cmdlet with `Get-Alias -Name`.

#### Graphical User Interface

```powershell-session
PS C:\htb> New-Alias -Name "Show-Files" Get-ChildItem
PS C:\> Get-Alias -Name "Show-Files"

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           Show-Files
```

PowerShell has a help system for cmdlets, functions, scripts, and concepts. This is not installed by default, but we can either run the `Get-Help <cmdlet-name> -Online` command to open the online help for a cmdlet or function in our web browser. We can type `Update-Help` to download and install help files locally.

#### Graphical User Interface

```powershell-session
PS C:\htb> help

TOPIC
    Windows PowerShell Help System
```

Typing a command such as `Get-Help Get-AppPackage` will return just the partial help unless the Help files are installed.

```powershell-session
PS C:\htb>  Get-Help Get-AppPackage
```

## Running Scripts

The PowerShell ISE (Integrated Scripting Environment) allows users to write PowerShell scripts on the fly. It also has an autocomplete/lookup function for PowerShell commands. The PowerShell ISE allows us to write and run scripts in the same console, which allows for quick debugging.

We can run PowerShell scripts in a variety of ways. If we know the functions, we can run the script either locally or after loading into memory with a download cradle like the below example.

Graphical User Interface

```powershell-session
PS C:\htb> .\PowerView.ps1;Get-LocalGroup |fl
```

One common way to work with a script in PowerShell is to import it so that all functions are then available within our current PowerShell console session: `Import-Module .\PowerView.ps1`. We can then either start a command and cycle through the options or type `Get-Module` to list all loaded modules and their associated commands.

```powershell-session
PS C:\htb> Get-Module | select Name,ExportedCommands | fl
```

One common way to work with a script in PowerShell is to import it so that all functions are then available within our current PowerShell console session: `Import-Module .\PowerView.ps1`. We can then either start a command and cycle through the options or type `Get-Module` to list all loaded modules and their associated commands.

```powershell-session
PS C:\htb> Get-Module | select Name,ExportedCommands | fl
```

## Execution Policy

Sometimes we will find that we are unable to run scripts on a system. This is due to a security feature called the `execution policy`, which attempts to prevent the execution of malicious scripts. The possible policies are:

|**Policy**|**Description**|
|---|---|
|`AllSigned`|All scripts can run, but a trusted publisher must sign scripts and configuration files. This includes both remote and local scripts. We receive a prompt before running scripts signed by publishers that we have not yet listed as either trusted or untrusted.|
|`Bypass`|No scripts or configuration files are blocked, and the user receives no warnings or prompts.|
|`Default`|This sets the default execution policy, `Restricted` for Windows desktop machines and `RemoteSigned` for Windows servers.|
|`RemoteSigned`|Scripts can run but requires a digital signature on scripts that are downloaded from the internet. Digital signatures are not required for scripts that are written locally.|
|`Restricted`|This allows individual commands but does not allow scripts to be run. All script file types, including configuration files (`.ps1xml`), module script files (`.psm1`), and PowerShell profiles (`.ps1`) are blocked.|
|`Undefined`|No execution policy is set for the current scope. If the execution policy for ALL scopes is set to undefined, then the default execution policy of `Restricted` will be used.|
|`Unrestricted`|This is the default execution policy for non-Windows computers, and it cannot be changed. This policy allows for unsigned scripts to be run but warns the user before running scripts that are not from the local intranet zone.|

Below is an example of the current execution policy for all scopes.

```powershell-session
PS C:\htb> Get-ExecutionPolicy -List
```

The execution policy is not meant to be a security control that restricts user actions. A user can easily bypass the policy by either typing the script contents directly into the PowerShell window, downloading and invoking the script, or specifying the script as an encoded command. It can also be bypassed by adjusting the execution policy (if the user has the proper rights) or setting the execution policy for the current process scope (which can be done by almost any user as it does not require a configuration change and will only be set for the duration of the user's session).

Below is an example of changing the execution policy for the current process (session).

```powershell-session
PS C:\htb> Set-ExecutionPolicy Bypass -Scope Process
```

# Windows Management Instrumentation (WMI)

WMI is a subsystem of PowerShell that provides system administrators with powerful tools for system monitoring. The goal of WMI is to consolidate device and application management across corporate networks. WMI is a core part of the Windows operating system and has come pre-installed since Windows 2000. It is made up of the following components:

|**Component Name**|**Description**|
|---|---|
|WMI service|The Windows Management Instrumentation process, which runs automatically at boot and acts as an intermediary between WMI providers, the WMI repository, and managing applications.|
|Managed objects|Any logical or physical components that can be managed by WMI.|
|WMI providers|Objects that monitor events/data related to a specific object.|
|Classes|These are used by the WMI providers to pass data to the WMI service.|
|Methods|These are attached to classes and allow actions to be performed. For example, methods can be used to start/stop processes on remote machines.|
|WMI repository|A database that stores all static data related to WMI.|
|CIM Object Manager|The system that requests data from WMI providers and returns it to the application requesting it.|
|WMI API|Enables applications to access the WMI infrastructure.|
|WMI Consumer|Sends queries to objects via the CIM Object Manager.|Some of the uses for WMI are:

- Status information for local/remote systems
- Configuring security settings on remote machines/applications
- Setting and changing user and group permissions
- Setting/modifying system properties
- Code execution
- Scheduling processes
- Setting up logging

These tasks can all be performed using a combination of PowerShell and the WMI Command-Line Interface (WMIC). WMI can be run via the Windows command prompt by typing `WMIC` to open an interactive shell or by running a command directly such as `wmic computersystem get name` to get the hostname. We can view a listing of WMIC commands and aliases by typing `WMIC /?`.

```cmd-session
C:\htb> wmic /?
```

The following command example lists information about the operating system.

```cmd-session
C:\htb> wmic os list brief

BuildNumber  Organization  RegisteredUser  SerialNumber             SystemDirectory      Version
19041                      Owner           00123-00123-00123-AAOEM  C:\Windows\system32  10.0.19041
```

WMIC uses aliases and associated verbs, adverbs, and switches. The above command example uses `LIST` to show data and the adverb `BRIEF` to provide just the core set of properties. An in-depth listing of verbs, switches, and adverbs is available [here](https://docs.microsoft.com/en-us/windows/win32/wmisdk/wmic). WMI can be used with PowerShell by using the `Get-WmiObject` [module](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1). This module is used to get instances of WMI classes or information about available classes. This module can be used against local or remote machines.

Here we can get information about the operating system.

```powershell-session
PS C:\htb> Get-WmiObject -Class Win32_OperatingSystem | select SystemDirectory,BuildNumber,SerialNumber,Version | ft

SystemDirectory     BuildNumber SerialNumber            Version
---------------     ----------- ------------            -------
C:\Windows\system32 19041       00123-00123-00123-AAOEM 10.0.19041
```

We can also use the `Invoke-WmiMethod` [module](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/invoke-wmimethod?view=powershell-5.1), which is used to call the methods of WMI objects. A simple example is renaming a file. We can see that the command completed properly because the `ReturnValue` is set to 0.

```powershell-session
PS C:\htb> Invoke-WmiMethod -Path "CIM_DataFile.Name='C:\users\public\spns.csv'" -Name Rename -ArgumentList "C:\Users\Public\kerberoasted_users.csv"
```

This section provides a brief overview of `WMI`, `WMIC`, and combining `WMIC` and `PowerShell`. `WMI` has a wide variety of uses for both blue team and red team operators. Later sections of this course will show some ways that `WMI` can be leveraged offensively for both enumeration and lateral movement.

# Microsoft Management Console (MMC)

The MMC can be used to group snap-ins, or administrative tools, to manage hardware, software, and network components within a Windows host. It has been around since Windows Server 2000 and runs on all Windows versions. We can also use MMC to create custom tools and distribute them to users. MMC works with the concept of snap-ins, allowing administrators to create a customized console with only the administrative tools needed to manage several services. These snap-ins can be added to manage both local and remote systems.

We can open MMC by just typing `mmc` in the Start menu. When we open MMC for the first time, it will be blank.

# Windows Subsystem for Linux (WSL)

[WSL](https://docs.microsoft.com/en-us/windows/wsl/) is a feature that allows Linux binaries to be run natively on Windows 10 and Windows Server 2019. It was originally intended for developers who needed to run Bash, Ruby, and native Linux command-line tools such as `sed`, `awk`, `grep`, etc., directly on their Windows workstation. The second version of WSL, released in May 2019, introduced a real Linux kernel utilizing a subset of Hyper-V features.

WSL can be installed by running the PowerShell command `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux` as an Administrator. Once this feature is enabled, we can either download a Linux distro from the Microsoft Store and install it or manually download the Linux distro of our choice and unpack and install it from the command line.

WSL installs an application called `Bash.exe`, which can be run by merely typing `bash` into a Windows console to spawn a Bash shell. We have the full look and feel of a Linux host from this shell, including the standard Linux directory structure.

```powershell-session
PS C:\htb> ls /

bin dev home lib lLib64 media opt root sbin srv tmp var
boot etc init 1lib32 Libx32 mnt proc run Snap sys usr
```

We can access the C$ volume and other volumes on the host operating system via the `mnt` directory, making the transition from the WSL host and the Windows host OS seamless. Once in this bash shell, we can interact with WSL as we would interact with any Linux-based operating system: running commands, installing updates/packages, etc.

```powershell-session
PS C:\htb> uname -a

Linux WS01 4.4.0-18362-Microsoft #476-Microsoft Frit Nov 01 16:53:00
PST 2019 x86_64 x86 _64 x86_64 GNU/Linux
```

# Desktop Experience vs. Server Core

[Windows Server Core](https://docs.microsoft.com/en-us/windows-server/administration/server-core/what-is-server-core) was first released with Windows Server 2008 as a minimalistic Server environment only containing key Server functionality. As a result, Server Core has lower management requirements, a smaller attack surface, and uses less disk space and memory than its Desktop Experience (GUI) counterpart. In Server Core, all configuration and maintenance tasks are performed via the command-line, PowerShell, or remote management with MMC or Remote Server Administration Tools (RSAT).

While Server Core aims to have a smaller footprint by lacking a GUI, some graphical programs are still supported, such as Registry Editor, Notepad, System Information, Windows Installer, Task Manager, and PowerShell. It also supports some Sysinternals suite tools such as Active Directory Explorer, Process Explorer, Process Monitor, and TCPView.

As of Windows Server 2019, Server Core or Desktop Experience must be selected at installation, and neither can be rolled back (i.e., converting Server Core to Desktop Experience). Once installed, the initial setup for Server Core can be done via `Sconfig`, which is a text-based interface (actually a VBScript executed by WScript). `Sconfig` is used for performing a variety of common commands such as configuring networking, checking for/installing Windows updates, account management, configuring remote management, activating Windows, and more.

Certain server applications cannot run on Server Core, including Microsoft Server Virtual Machine Manager 2019 (SCVMM), System Center Data Protection Manager 2019, SharePoint Server 2019, Project Server 2019.

In summary, Server Core is lighter weight and less resource-intensive but has a steeper learning curve and can be more difficult to manage. It also has some limitations, such as performing management tasks using certain GUI programs.

In any environment, the determination between using Desktop Experience or Server Core for a server installation should be made by both the business need and intended use of the server and the skill level of the administrators responsible for maintaining it. The following table shows some of the applications available on Server Core vs. Desktop Experience. This is a list of common applications and not an exhaustive list.

|**Application**|**Server Core**|**Desktop Experience**|
|---|---|---|
|Command prompt|Available|Available|
|Windows PowerShell/ Microsoft .NET|Available|Available|
|Regedit|Available|Available|
|Diskmgmt.msc|Not Available|Available|
|Server Manager|Not Available|Available|
|Mmc.exe|Not Available|Available|
|Eventvwr|Not Available|Available|
|Services.msc|Not Available|Available|
|Control Panel|Not Available|Available|
|Windows Explorer|Not Available|Available|
|Taskmgr|Available|Available|
|Internet Explorer or Edge|Not Available|Available|
|Remote Desktop Services|Available|Available|

# Windows Security
## Security Identifier (SID)

Each of the security principals on the system has a unique security identifier (SID). The system automatically generates SIDs. This means that even if, for example, we have two identical users on the system, Windows can distinguish the two and their rights based on their SIDs. SIDs are string values with different lengths, which are stored in the security database. These SIDs are added to the user's access token to identify all actions that the user is authorized to take.

A SID consists of the Identifier Authority and the Relative ID (RID). In an Active Directory (AD) domain environment, the SID also includes the domain SID.

```powershell-session
PS C:\htb> whoami /user

USER INFORMATION
----------------

User Name           SID
=================== =============================================
ws01\bob S-1-5-21-674899381-4069889467-2080702030-1002
```

The SID is broken down into this pattern.

```powershell-session
(SID)-(revision level)-(identifier-authority)-(subauthority1)-(subauthority2)-(etc)
```

Let's break down the SID piece by piece.

|**Number**|**Meaning**|**Description**|
|---|---|---|
|S|SID|Identifies the string as a SID.|
|1|Revision Level|To date, this has never changed and has always been `1`.|
|5|Identifier-authority|A 48-bit string that identifies the authority (the computer or network) that created the SID.|
|21|Subauthority1|This is a variable number that identifies the user's relation or group described by the SID to the authority that created it. It tells us in what order this authority created the user's account.|
|674899381-4069889467-2080702030|Subauthority2|Tells us which computer (or domain) created the number|
|1002|Subauthority3|The RID that distinguishes one account from another. Tells us whether this user is a normal user, a guest, an administrator, or part of some other group|

## Security Accounts Manager (SAM) and Access Control Entries (ACE)

SAM grants rights to a network to execute specific processes.

The access rights themselves are managed by Access Control Entries (ACE) in Access Control Lists (ACL). The ACLs contain ACEs that define which users, groups, or processes have access to a file or to execute a process, for example.

The permissions to access a securable object are given by the security descriptor, classified into two types of ACLs: the `Discretionary Access Control List (DACL)` or `System Access Control List (SACL)`. Every thread and process started or initiated by a user goes through an authorization process. An integral part of this process is access tokens, validated by the Local Security Authority (LSA). In addition to the SID, these access tokens contain other security-relevant information. Understanding these functionalities is an essential part of learning how to use and work around these security mechanisms during the privilege escalation phase.

## User Account Control (UAC)

[User Account Control (UAC)](https://docs.microsoft.com/en-us/windows/security/identity-protection/user-account-control/how-user-account-control-works) is a security feature in Windows to prevent malware from running or manipulating processes that could damage the computer or its contents. There is the Admin Approval Mode in UAC, which is designed to prevent unwanted software from being installed without the administrator's knowledge or to prevent system-wide changes from being made. Surely you have already seen the consent prompt if you have installed a specific software, and your system has asked for confirmation if you want to have it installed. Since the installation requires administrator rights, a window pops up, asking you if you want to confirm the installation. With a standard user who has no rights for the installation, execution will be denied, or you will be asked for the administrator password. This consent prompt interrupts the execution of scripts or binaries that malware or attackers try to execute until the user enters the password or confirms execution.

## Registry

The [Registry](https://en.wikipedia.org/wiki/Windows_Registry) is a hierarchical database in Windows critical for the operating system. It stores low-level settings for the Windows operating system and applications that choose to use it. It is divided into computer-specific and user-specific data. We can open the Registry Editor by typing `regedit` from the command line or Windows search bar.

The tree-structure consists of main folders (root keys) in which subfolders (subkeys) with their entries/files (values) are located. There are 11 different types of values that can be entered in a subkey.

| **Value** | **Type** |
| ---- | ---- |
| REG_BINARY | Binary data in any form. |
| REG_DWORD | A 32-bit number. |
| REG_DWORD_LITTLE_ENDIAN | A 32-bit number in little-endian format. Windows is designed to run on little-endian computer architectures. Therefore, this value is defined as REG_DWORD in the Windows header files. |
| REG_DWORD_BIG_ENDIAN | A 32-bit number in big-endian format. Some UNIX systems support big-endian architectures. |
| REG_EXPAND_SZ | A null-terminated string that contains unexpanded references to environment variables (for example, "%PATH%"). It will be a Unicode or ANSI string depending on whether you use the Unicode or ANSI functions. To expand the environment variable references, use the [**ExpandEnvironmentStrings**](https://docs.microsoft.com/en-us/windows/win32/api/processenv/nf-processenv-expandenvironmentstringsa) function. |
| REG_LINK | A null-terminated Unicode string containing the target path of a symbolic link created by calling the [**RegCreateKeyEx**](https://docs.microsoft.com/en-us/windows/desktop/api/Winreg/nf-winreg-regcreatekeyexa) function with REG_OPTION_CREATE_LINK. |
| REG_MULTI_SZ | A sequence of null-terminated strings, terminated by an empty string (\0). The following is an example: _String1_\0_String2_\0_String3_\0_LastString_\0\0 The first \0 terminates the first string, the second to the last \0 terminates the last string, and the final \0 terminates the sequence. Note that the final terminator must be factored into the length of the string. |
| REG_NONE | No defined value type. |
| REG_QWORD | A 64-bit number. |
| REG_QWORD_LITTLE_ENDIAN | A 64-bit number in little-endian format. Windows is designed to run on little-endian computer architectures. Therefore, this value is defined as REG_QWORD in the Windows header files. |
| REG_SZ | A null-terminated string. This will be either a Unicode or an ANSI string, depending on whether you use the Unicode or ANSI functions. |

Each folder under `Computer` is a key. The root keys all start with `HKEY`. A key such as `HKEY-LOCAL-MACHINE` is abbreviated to `HKLM`. HKLM contains all settings that are relevant to the local system. This root key contains six subkeys like `SAM`, `SECURITY`, `SYSTEM`, `SOFTWARE`, `HARDWARE`, and `BCD`, loaded into memory at boot time (except `HARDWARE` which is dynamically loaded).

The entire system registry is stored in several files on the operating system. You can find these under `C:\Windows\System32\Config\`.

The user-specific registry hive (HKCU) is stored in the user folder (i.e., `C:\Users\<USERNAME>\Ntuser.dat`).

## Run and RunOnce Registry Keys

There are also so-called registry hives, which contain a logical group of keys, subkeys, and values to support software and files loaded into memory when the operating system is started or a user logs in. These hives are useful for maintaining access to the system. These are called [Run and RunOnce registry keys](https://docs.microsoft.com/en-us/windows/win32/setupapi/run-and-runonce-registry-keys).

The Windows registry includes the following four keys:

```powershell-session
HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\RunOnce
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunOnce
```

Here is an example of the `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run` key while logged in to a system.

```powershell-session
PS C:\htb> reg query HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run
```

Here is an example of the `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run` showing applications running under the current user while logged in to a system.

```powershell-session
PS C:\htb> reg query HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
```

## Application Whitelisting

An application whitelist is a list of approved software applications or executables allowed to be present and run on a system. The goal is to protect the environment from harmful malware and unapproved software that does not align with the specific business needs of an organization. Implementing an enforced whitelist can be a challenge, especially in a large network. An organization should implement a whitelist in audit mode initially to make sure that all necessary applications are whitelisted and not blocked by an error of omission, which can cause more problems than it fixes.

Blacklisting, in contrast, specifies a list of harmful or disallowed software/applications to block, and all others are allowed to run/be installed. Whitelisting is based on a "zero trust" principle in which all software/applications are deemed "bad" except for those specifically allowed. Maintaining a whitelist generally has less overhead as a system administrator will only need to specify what is allowed and not constantly update a "blacklist" with new malicious applications.

Whitelisting is recommended by organizations such as [NIST](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-167.pdf), especially in high-security environments.

## AppLocker

[AppLocker](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview) is Microsoft's application whitelisting solution and was first introduced in Windows 7. AppLocker gives system administrators control over which applications and files users can run. It gives granular control over executables, scripts, Windows installer files, DLLs, packaged apps, and packed app installers.

It allows for creating rules based on file attributes such as the publisher's name (which can be derived from the digital signature), product name, file name, and version. Rules can also be set up based on file paths and hashes. Rules can be applied to either security groups or individual users, based on the business need. AppLocker can be deployed in audit mode first to test the impact before enforcing all of the rules.

## Local Group Policy

Group Policy allows administrators to set, configure, and adjust a variety of settings. In a domain environment, group policies are pushed down from a Domain Controller onto all domain-joined machines that Group Policy objects (GPOs) are linked to. These settings can also be defined on individual machines using Local Group Policy.

Group Policy can be configured locally, in both domain environments and non-domain environments. Local Group Policy can be used to tweak certain graphical and network settings that are otherwise not accessible via the Control Panel. It can also be used to lock down an individual computer policy with stringent security settings, such as only allowing certain programs to be installed/run or enforcing strict user account password requirements.

We can open the Local Group Policy Editor by opening the Start menu and typing `gpedit.msc`. The editor is split into two categories under Local Computer Policy - `Computer Configuration` and `User Configuration`.

For example, we can open the Local Computer Policy to enable Credential Guard by enabling the setting `Turn On Virtualization Based Security`. Credential Guard is a feature in Windows 10 that protects against credential theft attacks by isolating the operating system's LSA process.

We can use the PowerShell cmdlet `Get-MpComputerStatus` to check which protection settings are enabled.

```powershell-session
PS C:\htb> Get-MpComputerStatus | findstr "True"
```

 1. 1 Find the SID of the bob.smith user.
	+ cmd
	+ c:\Users\htb-student> wmic useraccount get name, sid
2.  What 3rd party security application is disabled at startup for the current user? (The answer is case sensitive).
	1. cmd `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`


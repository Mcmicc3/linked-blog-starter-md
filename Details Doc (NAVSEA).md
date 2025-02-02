1. Network Diagram

2. I uploaded an example to the OneDrive file share…in addition to the screenshot. Unsure if our Visio diagrams are out of sync in version with yours…
3. This is purely a generic demo but if you are looking at it I would say, consider zero trust between VLANs and these kinds of rules
	i.      Only Admin workstations interface with Admin Servers for making changes (read and write)

                                                             ii.      Admin Servers provide common services (DNS, NTP, Patches, Policy orchestrator, etc)

                                                           iii.      Any servers in the enclave can “read” from admin servers

                                                           iv.      Only Operator workstations and interface with Operator Servers to read/write commands

                                                             v.      Control System servers receive this info from operator servers

                                                           vi.      Only control system servers can interface with control systems

                                                          vii.      All of these comms between VLANs go through firewall, in addition to ACL

4. While not specified, assume a mixture of Windows Server and Red Hat Enterprise Linux  
      
      
      
      
    ![](file:///C:/Users/mcmic/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

5. Work Roles – Reference USN Cybersecurity Workforce and task list

6. [Navy COOL - CWF Workforce Model (osd.mil)](https://www.cool.osd.mil/usn/cswf/index.html)
7. [Navy COOL - System Administrator Qualification Matrix (osd.mil)](https://www.cool.osd.mil/usn/cswf/matrix.html?moc=cswf_sa_451)
8. [Navy COOL - Network Operations Specialist Qualification Matrix (osd.mil)](https://www.cool.osd.mil/usn/cswf/matrix.html?moc=cswf_nos_441)
9. [Navy COOL - Security Control Assessor Qualification Matrix (osd.mil)](https://www.cool.osd.mil/usn/cswf/matrix.html?moc=cswf_sca_612)
10. [Navy COOL - Vulnerability Assessment Analyst Qualification Matrix (osd.mil)](https://www.cool.osd.mil/usn/cswf/matrix.html?moc=cswf_vaa_541)
11. Note that for now we are loosely using these as the Navy implementation of CWF is going to change and be in pure alignment with DOD DCWF. The updates are coming out in April , essentially weve had to pigeon hole work roles for a while since the Navy only used a subset of the overall work roles (even though we were doing more). This will change.

12. Pentest Prep

13. Overarching Guiding docs…

                                                               i.      DOD Cyber Test and Evaluation Guidebook v2 - [https://ac.cto.mil/wp-content/uploads/2020/09/cyber-te-guide-v2c1.pdf](https://ac.cto.mil/wp-content/uploads/2020/09/cyber-te-guide-v2c1.pdf)

1.       This outlines what we have to do & when, in systems development

                                                             ii.      DOD Cyber Tabletop Guidebook - [https://ac.cto.mil/wp-content/uploads/2021/09/DoD-Cyber-Table-Top-Guide-v2.pdf](https://ac.cto.mil/wp-content/uploads/2021/09/DoD-Cyber-Table-Top-Guide-v2.pdf)

1.       Prior to a pentest we usually run a tabletop. Its good as an initial standalone event, but also helpful in analyzing and understanding the system and what “low hanging” fruit exists.

14. I still need to work with my lead to help scrub an example prep form. We do something called a “Local Test Event” approval which covers the test, assets, rules of engagement, and sanitization. I can not directly share the template but we can perhaps make a variant of it. In general, you plan and get approval before a pentest, and stick to what is approve ROE and do not deviate from it. Once done, clean it up.

Adding a SCADA piece

[https://github.com/Fortiphyd/GRFICSv2](https://github.com/Fortiphyd/GRFICSv2)

This version of GRFICS is organized as 5 VirtualBox VMs (a 3D simulation, a soft PLC, an HMI, a pfsense firewall, and a workstation) communicating with each other on host-only virtual networks. For a more detailed explanation of the entire framework and some background information on ICS networks, please refer to the workshop paper located at [https://www.usenix.org/conference/ase18/presentation/formby](https://www.usenix.org/conference/ase18/presentation/formby)

A video series walking through VM setup and example attacks is available on the Fortiphyd YouTube channel at [https://www.youtube.com/playlist?list=PL2RSrzaDx0R670yPlYPqM51guk3bQjFG5](https://www.youtube.com/playlist?list=PL2RSrzaDx0R670yPlYPqM51guk3bQjFG5)

NOS 3

[https://www.nasa.gov/nasa-operational-simulation-for-small-satellites/](https://www.nasa.gov/nasa-operational-simulation-for-small-satellites/)

The [**NASA Operational Simulation for Small Satellites (NOS3)**](http://www.nos3.org/) was developed by the JSTAR team in response to the [**STF-1**](https://www.nasa.gov/centers/ivv/jstar/stf1.html) mission. NOS3 allows for multiple developers to build and test flight software with simulated hardware models.  The flight software has no knowledge that it’s not actually being run in space, as it obtains all the same inputs that it would during nominal operations.

[https://github.com/sahana/eden](https://github.com/sahana/eden)
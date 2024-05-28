en
conf t
hostname Floor7
enable secret class
service password-encryption
no ip domain-lookup
banner motd 


line con 0
password cisco
login local
logging synchronous
exit

line vty 0 15
password cisco
login local
logging synchronous
exit

vlan 5
name Native_VLAN
vlan 10
name Financs
vlan 20
name Sales
vlan 30
name HR
vlan 40
name Management
vlan 50
name NetAdmin
vlan 60
name Guest 
no vlan 99

interface vlan 10
description Finance
ip address 10.20.70.2 255.255.255.192
no shut

interface vlan 20
description Sales
ip address 10.20.70.66 255.255.255.192
no shut

interface vlan 30
description HR
ip address 10.20.70.130 255.255.255.224
no shut

interface vlan 40
description Management
ip address 10.20.70.162 255.255.255.224
no shut

interface vlan 50
description NetAdmin
ip address 10.20.70.194 255.255.255.240
no shut

interface vlan 60
description Guest WIFI
ip address 10.20.70.210 255.255.255.240
no shut

int range fa1/0/1-6
switchport mode access
switchport access vlan 10

int range fa1/0/7-11
switchport mode access
switchport access vlan 20

int range fa1/0/12-14
switchport mode access
switchport access vlan 30

int range fa1/0/15-17
switchport mode access
switchport access vlan 40

int fa1/0/18-19
switchport mode access
switchport access vlan 50

int fa1/0/20-21
switchport mode access
switchport access vlan 60

int fa1/0/48
switchport trunk encapsulation dot1q
switchport mode trunk
switchport trunk native vlan 5
switchport trunk allowed vlan 10,20,30,40,50,60

conf t
ip domain-name ist4210-Lab.com
username admin privilege 15 secret sshadmin
line vty 0 15
transport input ssh
login local
crypto key generate rsa general-keys modulus 1024
exit

ip dhcp pool vlan10
network 10.20.70.0 255.255.255.192
default-router 10.20.70.1

ip dhcp pool vlan20
network 10.20.70.64 255.255.255.192
default-router 10.20.70.65

ip dhcp pool vlan30
network 10.20.70.128 255.255.255.224
default-router 10.20.70.129

ip dhcp pool vlan40
network 10.20.70.160 255.255.255.224
default-router 10.20.70.161

ip dhcp pool vlan50
network 10.20.70.192 255.255.255.240
default-router 10.20.70.193

ip dhcp pool vlan60
network 10.20.70.208 255.255.255.240
default-router 10.20.70.209

ip dhcp excluded-address 10.20.70.1 10.20.70.3
ip dhcp excluded-address 10.20.70.63
ip dhcp excluded-address 10.20.70.64 10.20.70.67
ip dhcp excluded-address 10.20.70.127
ip dhcp excluded-address 10.20.70.128 10.20.70.131
ip dhcp excluded-address 10.20.70.159
ip dhcp excluded-address 10.20.70.160 10.20.70.163
ip dhcp excluded-address 10.20.70.191
ip dhcp excluded-address 10.20.70.208 10.20.70.211
ip dhcp excluded-address 10.20.70.223
ip dhcp excluded-address 10.20.70.192 10.20.70.195
ip dhcp excluded-address 10.20.70.207

exit
int range fa1/0/22 - 47
shutdown
end
copy run start

#RememberToCloseUnusedPorts







































































































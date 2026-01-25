en
conf t
hostname 008042782
enable secret class
service password-encryption
no ip domain-lookup
banner motd 


line con 0
password cisco
login
logging synchronous
exit

line vty 0 15
password cisco
login
logging synchronous
exit

vlan 10
name Finance
vlan 20
name Sales
vlan 30
name HR
vlan 40
name Management
vlan 50
name NT_Admin
vlan 60
name Guest
vlan 99
name Native_VLAN

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
ip address 10.20.70.130 255.255.255.192
no shut

interface vlan 40
description Management
ip address 10.20.70.194 255.255.255.224
no shut

interface vlan 50
description NT Admin
ip address 10.20.70.226 255.255.255.240
no shut

interface vlan 60
description WAP
ip address 10.20.70.242 255.255.255.248
no shut

int range fa1/0/1-6
switchport mode access
switchport access vlan 10

int range fa1/0/7-11
switchport mode access
switchport access vlan 20

int range fa1/0/12-15
switchport mode access
switchport access vlan 30

int range fa1/0/16-17
switchport mode access
switchport access vlan 40

int fa1/0/18
switchport mode access
switchport access vlan 50

int fa1/0/20
switchport mode access
switchport access vlan 60

int g1/0/1
switchport trunk encapsulation dot1q
switchport mode trunk
switchport trunk native vlan 99
switchport trunk allowed vlan 10,20,30,40,50,60

conf t
ip domain-name ist4210-Lab.com
username admin privilege 15 secret sshadmin
line vty 0 15
transport input ssh
login local
crypto key generate rsa general-keys modulus 1024
exit

end
copy run start









































































































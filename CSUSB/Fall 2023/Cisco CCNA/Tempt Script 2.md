exo
en
config t
ip dhcp excluded-address 192.168.10.1 192.168.10.10
ip dhcp excluded-address 192.168.30.1 192.168.30.10
ip dhcp pool R1-LAN
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
dns-server 192.168.20.254
exit
ip dhcp pool R3-LAN
network 192.168.30.0 255.255.255.0
default-router 192.168.30.1
dns-server 192.168.20.254

en
conf ter
int g0/0
ip helper-address 10.1.1.2

en 
conf ter 
int g0/0
ip helper-address 10.2.2.2

en 
conf t
int g0/1
ip address dhcp
no shutdown
exit
show ip interface brief
show ip dhcp binding



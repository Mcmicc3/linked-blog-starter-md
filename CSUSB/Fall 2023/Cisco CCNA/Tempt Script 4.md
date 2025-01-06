![[Trash/SYNC/Images/Pasted image 20231022182933.png]]
![[Trash/SYNC/Images/Pasted image 20231022183014.png]]
en
conf ter
int ga0/1
no shutdown
int ga0/1.15
encapsulation dot1q 15
ip address 192.168.45.64 255.255.255.192
int ga0/1.30
encapsulation dot1q 30
ip address 192.168.45.128 255.255.255.192
ip dhcp pool LAN 
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
dns-server 192.168.20.254
int ga0/1.45
encapsulation dot1q 45
ip address 192.168.45.16 255.255.255.240
int ga0/1.60
encapsulation dot1q 60
ip address 192.168.45.64 255.255.255.240


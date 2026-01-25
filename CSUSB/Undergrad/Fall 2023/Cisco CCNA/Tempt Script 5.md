
access-list 10 permit 192.168.30.0 0.0.0.255

access-list 1 permit 192.168.10.10 0.0.0.0
access-list 1 permit host 192.168.10.10
access-list 1 permit 0.0.0.0 255.255.255.255
access-list 1 permit any

Standard ACL should be closest to the destination
Extended ACL should be closest to the source

remark "Used as a description"

access-list 120 remark This ACL allows Sales from all floors to communicate with floor 7 Sales
access-list 120 permit tcp 10.20.10.0 0.0.0.63 10.20.70.0 0.0.0.63 
int range g1/0/1-2
ip access-group 1020 in

|   |   |
|---|---|
|Command|Description|
|Router(config)#**ip access-list standard 1**|Creates or edits a standard access list using an ID number of 1.|
|Router(config)#**10 deny 192.168.0.0 0.255.255.255**|Assigns the sequence number of 10 to the deny statement.|

Router(config)#**access-list 1 deny 10.0.0.0 0.255.255.255**
Router(config)#**access-list 1 permit any**
Router(config)#**interface fa0/0**
Router(config-if)#**ip access-group 1 out**
Router(config-if)#**end**
Router#

Router#**configure terminal**
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#**ip access-list standard block-network**
Router(config-std-nacl)#**deny 172.16.20.0 0.0.0.255**
Router(config-std-nacl)#**permit any**
Router(config)#**interface fa0/0**
Router(config-if)#**ip access-group block-network out**
Router(config-std-nacl)#**end**

Router(config)#**access-list 12 permit 192.168.1.0 0.0.0.255**
Router(config)#**line vty 0 4**
Router(config-line)#**access-class 12 in**

Router(config)#**access-list 111 deny tcp any any eq 20**
Router(config)#**access-list 111 deny tcp any any eq 21**
Router(config)#**access-list 111 permit ip any any**
Router(config)#**int s0**
Router(config-if)#b

Router(config)#**access-list 101 deny ip 10.1.1.1 0.0.0.0 15.1.1.1 0.0.0.0**
Router(config)#**access-list 101 permit ip any any**
Router(config)#**int s1**
Router(config-if)#**ip access-group 101 in**
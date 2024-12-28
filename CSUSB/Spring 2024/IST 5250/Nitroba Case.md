WireShark PCAP capture

Professor


gets harassing emails, thinks it's a student in class.

Nitroba provides 10mpbs in every room

kenny installed wifi in the room?

Nitroba IT sets up a packet sniffer  {Where}

They waited, and the guy attacked

They recieved a "you can't find us" email
- Will self-destruct
- Stop teaching
- start running

Message gets destroyed

Class list

adivce

look at the PCAP, map out the dorm room
find out who sent the email
look for an IP address, and a TCP flow
Use TCP Packet, TCP flow, boom, it shows what they were doing.

Hope to find any log in identifiying information
Find ID's from those who attacked.

See if you can narrow it down.

#### Download the PCAP
Open it in Wireshark, 

Some poeple use TCP view to parse the PCAPs, but use Wireshark. Local to parse? Network miner, some people use that too. 

##### hint: Use AI friend to ask questions in how you would go about to figure this out
How should you look at this.



Network minor (purple pickaxe)

jcoachj@gmail.com

"hey johnny, rewards"

Lily's IP is most likely 192.168.15.4 {Did I write this?}


## Notes
Received IP address: 140.247.62.34 by mta368.mail.re4.yahoo.com with SMTP, from nobody@nitroba.org
personal email: lilytuckrige@yahoo.com
Subject headers: we don't like your class
Results from host 140.247.62.34:  34.62.247.140.in-addr.arpa domain name pointer **G24.student.nitroba.org**
G24 is most likely a dorm room: three people share that room: Alice, Barbara, and Candice.
No wifi is provided, but, Barbara's boyfriend Kenny installed a wifi router. 
**This router is connected to ethernet, is it getting an address from the school? Is the router on it's own subnet?**

Apple WIFI MAC Address: 00:17:f2:e2:c0:ce

## Filtering with frame contains "tuckrige"
![[Trash/SYNC/Images/Pasted image 20240326181231.png]]
Both emails source from **192.168.15.4**
Source port: 35876


Filters:
- frame contains "tuckrige" 
- ip.addr == {ip address}
- tcp.port == {port number}
- tcp.flags.push == 1
- http

## Following first frames http stream
`<a href="http://www.prockster.com" target="_blank">Access blocked sites or browse anonymously from work or school </a><br>
<br>
`<a href=index.php>Send some Anonymous Fake eCards</a><a href=http://www.sendanonymousemail.net>? </a><br>

##### amy789smith

A user under the name "amy789smith", authenticated with Yahoo, YMSG
- Could be Amy? She's in the class, but she's not part of the three people living in the same dorm.

### Ava Book? 
![[Trash/SYNC/Images/Pasted image 20240326185456.png]]


## Query for sendanonymousemail.net
![[Trash/SYNC/Images/Pasted image 20240326190222.png]]




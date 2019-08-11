*****check for up systems*****
nmap -sn for icmp echo scan
nmap ping sweep for range of ips  nmap -sn -PE -PA80,21,8080,443 192.168.151.0/24
nmap scan all ports in range of ips nmap -p 1-65535 -T4 -A 192.168.151.0/24
-----------

*********check for open ports*********
full open scan:(tcp connect scan)   nmap -sT -v 192.168.31.0/24 (scans all the ports)
half open scan:(stealth scan) nmap -sS -p 80 192.168.151.123 (used to see if port 80 is open) 
null scan: nmap -sN -p 1-65535 probe packet (fin,urg,psh,null) if ack then port is closed....if ack is recieved then port is closed
xmas scan: send fin,urg,psh packets together...does not work on windows system
xmas tree scan nmap -sX 
ack flag probe scanning:  if network has firewall...it will not allow the ack packet to reach the target nmap -sA -v 192.168.151.132
upd scan: if udp port 29 is open the no reply...if port is closed the ICMP port unreachable response nmap -sU -v -p 29 192.168.151.123
---------------------------------------

*******Scanning beyond IDS*******
fragment to avoid IDS : nmap -sS -T4 -A -f -v 192.168.151.133  fragment the packets into small pieces so that the IDS cant understand the packet
----------------------

******Banner Scan****************
ID Serve for scanning the server's information.

counter-measure to change the banner information. 
turn off the server banner signature. 
hiding the page extension.
---------

*******MBSA**********
microsoft baseline security analyzer.
--------------------

**********NETWORK Diagram**********
lan state : draws a network diagram
----------------------------------

******Anonymizers******
tor : uses chain porxy 
cyber ghost: chain proxy
anonymizer: 
gzapper: identify google tracking id
--------------------

******Spoofing IP Address*******
nmap -S 192.165.0.174 -A -v 192.168.151.401   -S is for spoofed IP Address

counter-meausure: check network log.

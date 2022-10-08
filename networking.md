# Networking  



## Network Troubleshooting  

CLI Utilities: Ping, ARP, and Traceroute

IPconfig, Ping, ARP, and Route on Windows

Traceroute on Linux

CLI Utilities: NMAP, Netstat, NSLookup, and SSH

NMAP and Netstat

Scan with NMAP and Examine Netstat

NSLookup on Windows

NSLookup and Dig on Linux

Network Software Utilities

Capturing Traffic

Capture and Analyze Traffic with Wireshark

Capture Traffic with TCPDUMP on Linux

Bandwidth Testing

Scan Network Devices with IP Scanner

Moving Files with TFTP

Examine Netflow Data

Troubleshooting Layer 7 and Above Issues

Troubleshooting Routing Issues

Examine Routing Issues

Examine DNS issues

Examine NTP and Certificate Issues

Examine Host Based Firewall Issues



```

ifconfig 	Display and manipulate route and network interfaces.
ip 		It is a replacement of ifconfig command.
traceroute 	Network troubleshooting utility.
tracepath 	Similar to traceroute but doesn't require root privileges.
ping 		To check connectivity between two nodes.
netstat 	Display connection information.
ss 		It is a replacement of netstat.
dig 		Query DNS related information.
nslookup 	Find DNS related query.
route 		Shows and manipulate IP routing table.
host 		Performs DNS lookups.
arp 		View or add contents of the kernel's ARP table.
iwconfig 	Used to configure wireless network interface.
hostname 	To identify a network name.
curl or wget 	To download a file from internet.
mtr 		Combines ping and tracepath into a single command.
whois 		Will tell you about the website's whois.
ifplugstatus 	Tells whether a cable is plugged in or not.







    Syntax: nmap <scan type> <options> <target>

S.No 	Title 	Command Syntax 	POC (click to enlarge)

Target Selection

nmap 192.168.20.128 	  	Scan a single IP 	
nmap www.example.com 	  	Scan a host 	
nmap 192.168.20.120-128   	Scan a range of IPs 	
nmap 192.168.20.2/24 	  	Scan a subnet 	
nmap -iL ips.txt 	  	Scan targets from Text file 	

Port Selection

nmap -p 22 192.168.20.128 	Scan a single port 	
nmap -p 1-100 192.168.20.128 	Scan a range of ports 	
nmap -F 192.168.20.128 	        Scan 100 common ports 	
nmap -p- 192.168.20.128 	Scan all ports 	
nmap -p U:137,T:139 192.168.20.128 	Specify UDP or TCP scan 	

Scan Types

nmap -sT 192.168.20.128 		Scan using TCP connect 	
nmap -sS 192.168.20.128 		Scan using TCP SYN scan 	
nmap -sU -p 123,161,162 192.168.20.128 	Scan UDP ports 	
nmap -Pn -F 192.168.20.128 		Scan Selected ports (Ignore Discovery) 	

Service and OS Detection

nmap -A 192.168.20.128 		Detect OS and Services 	
nmap -sV 192.168.20.128 	Standard service detection 	
nmap -sV --version-intensity 5 192.168.20.128 	Aggressive service detection 	

Output Formats

nmap -oN result.txt 192.168.20.128 	Save default output to file 	
nmap -oX resultxml.xml 192.168.20.128 	Save results as XML 	
nmap -oG formattable.txt 192.168.20.128 Save formatted results (Grep) 	
nmap -oA allformats 192.168.20.128 	Save in all formats 	

Scripting Engine

nmap -sV -sC 192.168.20.128 		Scan using default safe scripts 	
nmap --script-help=ssl-heartbleed 	Get help for a script 	
nmap -sV -p 443 -script=ssl-heartbleed 192.168.20.133 	Scan using a specific script 	
nmap --script-updatedb 			Update script database 	

Some Useful NSE Scripts

nmap -sU -A -PN -n -pU:19,53,123,161 -script=ntp-monlist,dns-recursion,snmp-sysdescr 192.168.20.2/24 					    	    Scan for UDP DDOS reflectors 	
nmap --script=http-title 192.168.20.128 		Gather page titles from HTTP Servers 	
nmap --script=http-headers 192.168.20.128 	Get HTTP headers of web services 	
nmap --script=http-enum 192.168.20.128 		Find web apps from known paths 	
nmap -sU --script nbtstat.nse -p 137 192.168.20.128 	 Find exposed Netbios servers 	



```

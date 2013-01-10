By:		Roger Svenning
Date:		2013-01-10
Program name:	find_ue9.pl

Usage:		./find_ue9

Verified on OS:	Ubuntu 11.10 on HP/Compaq 2510p
		Ubuntu image "2012-10-28-wheezy-raspbian.zip" on RaspberryPi board,
			sha1sum 2012-10-28-wheezy-raspbian.zip
			3ee33a94079de631dee606aebd655664035756be  2012-10-28-wheezy-raspbian.zip

Perl version:	v5.12.4	(Ubuntu 11.10 on HP/Compaq 2510p)
		v5.14.2 (Ubuntu on RaspberryPi board)

Note:		- The network interface on the computer must be on the same IP-subnet as the UE9.
		- There must be only one network interface active (up) on the computer.

The meaning with this program
-----------------------------
When running a LabJack UE9 on an IP-network, with the UE9 configured
to ask for an IP-address via DHCP, there might be an issue to find out
the IP-address that was given to it.

This program is meant to make it easy to find out.

For now, it is expected to find exaclty one UE9 on the local IP subnet.

How to get a copy from GITHub and run it
----------------------------------------
1.	You need to have git installed.

2.	With GIT installed, get a copy of find_ue9.pl like this.

		roger@tiny:~$ mkdir tmp
		roger@tiny:~/tmp$ git clone git://github.com/rsvenning/find_ue9.git

3.	Example of use.

		roger@tiny:~/tmp$ cd find_ue9
	
		roger@tiny:~/tmp/find_ue9$ ./find_ue9.pl 
			# Child,  lisening on port 52363 (UDP)
			# Parent, about to send broadcast, from IP-address: 192.168.1.100 to Broadcast-address: 192.168.1.255, Port: 52362
			# Child,  datagram received:
			UE9_IP_address  192.168.1.101
			UE9_IP_gateway  192.168.1.1
			UE9_IP_subnet   255.255.255.0
			UE9_portA       52360
			UE9_portB       52361
			UE9_MAC_address 00:50:c2:a0:89:76

Enjoy!
/Roger S

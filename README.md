
# TFN2K

The Tribe Flood Network or TFN is a set of computer programs to conduct various DDoS attacks such as ICMP flood, SYN flood, UDP flood and Smurf attack.

First TFN initiated attacks are described in CERT Incident Note 99-04.

TFN2K was written by Mixter, a security professional and hacker based in Germany.
# #

**Terminology**

The terminology used in DDoS analyses is often confusing. For clarity, we use the following:

* Client : an application that can be used to initiate attacks by sending commands to other components.

* Daemon : a process running on an agent (see below), responsible for receiving and carrying out commands issued by a client.

* Master  : a host running a client

* Agent  : a host running a daemon

* Target : the victim (a host or network) of a distributed attack

# #

**Overview - What is TFN2K?**  ▄︻̷̿┻̿═━一

TFN2K allows masters to exploit the resources of a number of agents in order to coordinate an attack against one or more designated targets.
Currently, UNIX, Solaris, and Windows NT platforms that are connected to the Internet, directly or indirectly, are susceptible to this attack.
However, the tool could easily be ported to additional platforms.

TFN2K is a two-component system: a command driven client on the master and a daemon process operating on an agent. The master instructs its agents to attack a list of designated targets.
The agents respond by flooding the targets with a barrage of packets. Multiple agents, coordinated by the master, can work in tandem during this attack to disrupt access to the target.
Master-to-agent communications are encrypted, and may be intermixed with any number of decoy packets.
Both master-to-agent communications and the attacks themselves can be sent via randomized TCP, UDP, and ICMP packets.
Additionally, the master can falsify its IP address (spoof).
These facts significantly complicate development of effective and efficient countermeasures for TFN2K.


Commands are sent from the master to the agent via TCP, UDP, ICMP, or all three at random. Targets may be attacked with a TCP/SYN, UDP, ICMP/PING, or BROADCAST PING (SMURF) packet flood.
The daemon may also be instructed to randomly alternate between all four styles of attack.
Packet headers between master and agent are randomized, with the exception of ICMP, which always uses a type code of ICMP_ECHOREPLY (ping response).

All control communications are unidirectional, making TFN2K extremely problematic to detect by active means.
Because it uses TCP, UDP, and ICMP packets that are randomized and encrypted, packet filtering and other passive countermeasures become impractical and inefficient.
Decoy packets also complicate attempts to track down other agents participating in the denial-of-service network.
# #

### =============== **usage** ===============

* git clone https://github.com/mohammad0021/TFN2K.git

# #

* cd TFN2K/src
![TFN2K](http://s9.picofile.com/file/8319916300/2.png)

# #

* make
> Do you agree to this disclaimer [y/n]? **`y`**   AND
> server key [8 - 32 chars]: **`00008421`**

![TFN2K](http://s9.picofile.com/file/8319916384/3.png)

# #

* ./tfn 
![TFN2K](http://s9.picofile.com/file/8319916742/4.png)


*｡◕‿◕｡*





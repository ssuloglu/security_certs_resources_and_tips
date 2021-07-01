# Host Enumeration

Discovering various information on a host would help in preparetion of exploits. Here are some examples of host information:
* OS version
* Users
* Services
* Groups
* Privileges
* Shares
* Configuration Settings


### Windows Enumeration Methods and Tools
Different ways to enumerate Windows host are explained in the following sections.
#### Built-in commands
##### Command Line
```
dir
ipconfig
arp
route
net share
net user
```
##### Powershell
```
Get-Website
Get-LocalUser
Get-LocalGroup
Get-LocalGroup
Get-Command
```
#### Nmap  
* OS dicovery: `> nmap -O <host ip>`
* Service Discovery: `> nmap -sV <host ip>`
* bulit in scripts: `> nmap <host ip> -script smb-os-discovery.nse`
#### Rpcclient
`rpcclient <host ip> -U admin`
#### Metasploit Framework


### Linux Enumeration Methods and Tools
#### Built-in commands
```
uname -a
hostname
route
arp
ifconfig
mount
whoami
```
##### Additional
* To find all SUID files: `find / -perm -4000 -type f 2>/dev/null`
* To list services that are running as root: `ps aux | grep root | less`

### Web Application Enumeration 
#### Wafw00f
Wafw00f is useful to decide whether the web application is behind a firewall or not. 
Usage:`> wafw00f <hostname>`
#### HTTPrint
Windows-based tool, can be downloadble from `www.net-square.com/httprint.html`
#### Nmap
`> nmap --script=http-enum <hostname>`


### SMB Enumeration
Different versions of Windows includes various versions of SMB. 

* SMB1 - Windows 2000, Windows XP, and Windows Server 2003
* SMB2 - Windows Vista SP1 and Windows Server 2008
* SMB2.1 - Windows 7 and Windows Server 2008 R2
* SMB3 - Windows 8 and above, Windows Server 2012 and above


1) To discover if SMB is served via nmap: `> nmap -v -p 139,445 <host ip>` 
2) To find out NetBIOS info, nbtscan is used: `> nbtscan -r <host ips>` 
	Example usage: `> nbtscan -r 192.168.0.0./24`
3) To check the security level of the SMB server: `> nmap -v -p 139,445 -script=smb-security-mode <host ip>`


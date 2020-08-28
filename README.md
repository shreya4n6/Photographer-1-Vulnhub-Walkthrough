# Photographer-1-Vulnhub-Walkthrough
Here is a walk through for Photographer:1 which is a vulnerable machine on Vulnhub. It was created by Shreya Talukdar. This machine was developed to prepare for OSCP. It is boot2root, tested on VirtualBox (but works on VMWare) and has two flags: user.txt and proof.txt.

Check out the docs provided !! :point_up::point_up::point_up:

# Enjoyyyyyy !! :smiley::smiley:

# nmap -sV : -sV: Probe open ports to determine service/version info
  --version-intensity <level>: Set from 0 (light) to 9 (try all probes)
  --version-light: Limit to most likely probes (intensity 2)
  --version-all: Try every single probe (intensity 9)
  --version-trace: Show detailed version scan activity (for debugging)

# SMB is a File Server protocol. 
Its primary purpose is to allow multiple users to read and write from the same file that is stored only on the File Server.

Using SMB means:

:point_right: the SMB client does not have to use any local storage to store a copy of the file. It can read and write data directly on the File Server.

:point_right: any changes that one user makes to the file are immediately visible to the other users of the same file. There is only a single file that is shared by multiple users.
:point_right: Moreover, the smbclient command is useful for both accessing files on a remote Microsoft Network or Samba server, and for testing the Samba services on your own server.
To connect to your server’s own Samba services from the command line as a test, enter the following command, where share is the name of the share you want to connect to (either a user’s login name or the word "root") and username is the username to log in as:

# > smbclient "\\localhost\share" -U username

# Why not Ftp ? We could have used ftp in place of smbclient.
FTP is a File Transfer protocol. Its primary purpose is to let users copy an entire file from one computer to another.

Using FTP means:

:point_right: The FTP client must have enough local storage space to store a copy of the entire file

:point_right: there are two separate copies of the file: the original file on the FTP server and the copy of the file on the FTP client. The two files are then independent: any changes in one copy of the file are not reflected in the other copy.

# What is a reverse shell ?
A shell is a user interface for access to operating system services. A reverse shell is a remote shell, where the connection is made from the system that offers the services to the client that wants to use these services.

# How does a reverse shell work ?
To create a reverse shell, you need to open a client machine port that is accessible from the Internet. Then, you need to run a listener on the client machine. Finally, you need to run a command on the server that establishes a connection with the client listener.

# How to block reverse shells ?
There is no way to completely block reverse shells. You can only make it more difficult to create one by blocking most outgoing ports (if possible) and turning off most services (if possible). You can also monitor all traffic outgoing from the server for potential shell commands.

# Nikto
Nikto is an open-source scanner and you can use it with any web servers (Apache, Nginx, IHS, OHS, Litespeed, etc.). Sounds like a perfect in-house tool for web server scanning. It is capable of scanning for over 6700 items to detect misconfiguration, risky files, etc. and some of the features include;

:point_right: You can save the report in HTML, XML, CSV
:point_right: It supports SSL
:point_right: Scan multiple ports on the server
:point_right: Find subdomain
:point_right: Apache user enumeration
:point_right: Checks for outdated components
:point_right: Detect parking sites

# nc - arbitrary TCP and UDP connections and listens
It can open TCP connections, send UDP packets, listen on arbitrary TCP and UDP ports(nc -l), do port scanning, and deal with both IPv4 and IPv6. Unlike telnet(1), nc scripts nicely, and separates error messages onto standard error instead of sending them to standard output, as telnet(1) does with some.
Common uses include:

:point_right: simple TCP proxies
:point_right: shell-script based HTTP clients and servers
:point_right: network daemon testing
:point_right: a SOCKS or HTTP ProxyCommand for ssh(1)

# python -c 'import pty;pty.spawn("/bin/bash")'
:point_right: pty stands for pseudoterminal . A device entry that acts like a terminal to the process reading and writing there but managed by something else.
:point_right: Spawn a process, and connect its controlling terminal with the current process's standard io.






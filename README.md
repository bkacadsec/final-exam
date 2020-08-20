# BKACAD Security Training - Final Exam

## Summary

Description | Requirement 
--- | --- 
Type of Exam | Open book examination
Duration | 120 mins
Number of Questions | 10
Passing Score | 8/10

## Submit your exam to below link

https://drive.google.com/drive/u/2/folders/1Iwp3SEApr-M1BEl3SD6E_nbhbMxb4w6V

### How to name final exam?

Eg: NguyenVanA.docx 

*please don't inject backdoor into this file ;)*

## Questions

### Question 01

List all elements of Information Security.

### Question 02

By using **"Google Hacking"** technique, compose a dork that will list all websites have D-LINK login panel.

Hint: D-LINK in title & /info/Login.html in URL

### Question 03

With **Nmap** tool, Scan all open ports, services and version of domain bkacad.com.

Note: Capture Nmap result as a image and attached to answer file.

### Question 04

Have following script named portScan.py

```python
# !/usr/bin/python

'''
TCP Port scanner with socket 
'''

import sys
#import socket

def scanner(target, port):
	s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
	s.settimeout(5)
	if s.connect_ex((target, port)) == 0:
		print "Port %d open" %(port)
	else:
		pass
	s.close()

def main():
	try:
		target = raw_input("Input your target: ")
		list_port = [80, 21, 22, 23, 443, 110]
		for port in list_of_port:
			scanner(target, port)
	except socket.error:
                print "Network error!"
        except KeyboardInterrupt:
                print "You pressed Ctrl+C"
                sys.exit()


if __name__ == "__main__":
	main()
```

Copy this source code, save and run with python. You need to find and trouble-shoot existed bug in this code. Your answer is the source code that run correctly.

### Question 05

Download [pcap](https://github.com/bkacadsec/sec/raw/master/chapter2/lecture5/http.pcap) file and then analyze with Wireshark.

Your answer is the password that you found in target file.

### Question 06

Using **Nessus** scan vulnerabilities at Metasploitable 2 machine. Export reporting file in PDF format.

Continue to exploit **vsftpd 2.3.4 - Backdoor Command Execution** at target machine.

Hint:

```
msfconsole
Search vsftpd
use exploit/unix/ftp/vsftpd_234_backdoor
```

The answer include:

* Reporting file
* Result after exploit target successfully

### Question 07

Provided /etc/passwd with contain

```txt
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/bin/sh
bin:x:2:2:bin:/bin:/bin/sh
sys:x:3:3:sys:/dev:/bin/sh
klog:x:103:104::/home/klog:/bin/false
sshd:x:104:65534::/var/run/sshd:/usr/sbin/nologin
msfadmin:x:1000:1000:msfadmin,,,:/home/msfadmin:/bin/bash
bind:x:105:113::/var/cache/bind:/bin/false
postfix:x:106:115::/var/spool/postfix:/bin/false
ftp:x:107:65534::/home/ftp:/bin/false
postgres:x:108:117:PostgreSQL administrator,,,:/var/lib/postgresql:/bin/bash
mysql:x:109:118:MySQL Server,,,:/var/lib/mysql:/bin/false
tomcat55:x:110:65534::/usr/share/tomcat5.5:/bin/false
distccd:x:111:65534::/:/bin/false
user:x:1001:1001:just a user,111,,:/home/user:/bin/bash
service:x:1002:1002:,,,:/home/service:/bin/bash
```

And /etc/shadow with contain

```txt
root:$1$/avpfBJ1$x0z8w5UF9Iv./DR9E9Lid.:14747:0:99999:7:::
daemon:*:14684:0:99999:7:::
bin:*:14684:0:99999:7:::
sys:$1$fUX6BPOt$Miyc3UpOzQJqz4s5wFD9l0:14742:0:99999:7:::
klog:$1$f2ZVMS4K$R9XkI.CmLdHhdUE3X9jqP0:14742:0:99999:7:::
sshd:*:14684:0:99999:7:::
msfadmin:$1$XN10Zj2c$Rt/zzCW3mLtUWA.ihZjA5/:14684:0:99999:7:::
bind:*:14685:0:99999:7:::
postfix:*:14685:0:99999:7:::
ftp:*:14685:0:99999:7:::
postgres:$1$Rw35ik.x$MgQgZUuO5pAoUvfJhfcYe/:14685:0:99999:7:::
mysql:!:14685:0:99999:7:::
tomcat55:*:14691:0:99999:7:::
distccd:*:14698:0:99999:7:::
user:$1$HESu9xrH$k.o3G93DGoXIiQKkPmUgZ0:14699:0:99999:7:::
service:$1$kR3ue7JZ$7GxELDupr5Ohp6cjZ3Bu//:14715:0:99999:7:::
```

With Attack password tools and techniques, crack password of user **sys**

### Question 08

Find Reflected XSS at https://fado.vn/ that will pop-up user's **cookie**.

With SQLmap, attack SQL injection at http://www.keenlight.com.hk/

The answer include:

* Payload + URL affected by XSS
* Screen-shot XSS pop-up in your browser
* Command that you used in SQL injection attack & creen-shot your result
* SQL injection attack require to dump user's credentials

### Question 09

At Metasploitable 2, add a normal user as *yourname* and do at least **two ways** to **privilege escalation to root**

Hint:

```
useradd Alice
passwd Alice
Enter new UNIX password: 
Retype new UNIX password: 
passwd: password updated successfully
```

### Question 10

Generate CSV injection backdoor with MSFvenom & Microsoft Excel.

The answer include:

* Show CSV injection payload
* Screen-shot Kali machine and Windows machine after victim open CSV injection backdoor

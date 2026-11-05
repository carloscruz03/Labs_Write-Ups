<div align="center">
  <img src="img/Laboratory-Meow.png" alt="Meow Machine" width="400">
</div>

### Decription

- Difficulty: Easy
- OS: Linux
- Task: Get on the target network

### About:

Meow is a very easy Linux machine which guides players on setting up their attacking machines, connecting to HTB labs via VPN and demonstrates the strategy of how to complete them. The machine focuses on beginner enumeration techniques and showcases the exploitation of a vulnerable Telnet service through default credentials.

### Procedure

The objective of this laboratory is to access the "Meow" machine with default credentials. By doing this I will be able to archive a .txt file with the flag that I need to provide. All of this will be done accesing the machine through a telnet connection, which is the older standard before ssh arrived.

I first entered the terminal, and used nmap to scan all the ports in the victim's machine with it's IP address 10.192.82.98 (provided by Hack The Box). By scanning the ports I have the knowledge to access the victim machine by a non protected port. 

Result of the scan:

<img src="img/Pasted%20image%2020260622094749.png" alt="Meow Machine" width="400">

I used the parameters -Pn and -F to improve the process:

```-Pn``` works for making a scan without sending a Ping. A Ping is a process where my machine sends a request via network the victim machine to detect if it's on. If there isn't any response the machine is off. Modern firewalls block Pings, so in order to scan the victim's machine bypassing the firewall I add the parameter -Pn, which configures nmap scan, to scan the machine without detecting if it's on or not. 

```-F``` is a paramater that configures the scan by reducing the number of ports being scanned. Normally there are thousands of ports, but with ```-F``` the number of ports to scan reduces to the 100 most common, which is very useful because often here's where the accesses exist.

The report made by nmap shows that there's a service running in the port 23/tcp. So know that I know that I proceed to use the telnet tool to access that port:

<img src="img/Pasted%20image%2020260622101350.png" alt="Acceso por Telnet" width="400">

After I provided the default credentials it granted me access, which I used to launch an ls command and see the files inside the machine. Finding the flag.txt file. I entered cat flag.txt to see the content of it, and got the flag:

<img src="img/Pasted%20image%2020260622103517.png" alt="Bandera capturada" width="400">

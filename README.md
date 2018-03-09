# Intro
This demo will teach how to scan a network using nmap. Nmap is a network mapper and will reveal open ports on machines on a subnet, or a target machine.  Nmap comes with several different scanning techniques that we will explore

 This will be a windows based demonstration but a copy of the mac nmap will be available too.  The nmap commands will remain the same in both OS, but command prompt commands can change.
# What we will do
1. Install nmap in order to run the scans
2. first check our host pc's ip address in order to learn the subnet for future scanning
3. Run through various scans and the results they return
# Steps
1. Clone repo
```
git clone https://github.com/hlindley33/Learn-Network-Scanning.git
```
2. Run the nmap-setup.exe
4. Select all nmap options and install nmap in your programs folder/
3. Open a command prompt (windows+r then type cmd and hit enter.)
4. First in the command prompt and run ifconfig
  * You will see a "Wireless LAN adapter Wi-Fi" and underneath it there will be an ipv4 address.
  * This address will help with subnet scanning later down the line
  * We will also use this address to run scans against our own computer
5. Now open another command prompt and we will begin our nmap Scanning.  My IP for this is 192.168.2.45, but wherever you see this IP replace it with your own.
  1. This scan will scan our own host computer and we can define the ports that it scans to see if they are Open. This scan scans port 25-80
  ```
  nmap 192.168.2.45 -p25-80
  ```
  2. This scan will scan the whole subnet that the host computer is on, and it will scan all ports
  ```
  nmap 192.168.2.0/24
  ```
  3. Now for network reconnaissance we do not always want the scans to seem to come from our host computer.  So it is possible to spoof the IP that is sending the scans, which will be shown in this example
  ```
  nmap 192.168.2.45 -D 10.0.0.1,10.0.0.2,10.0.0.3
  ```
  This will make the scans seem to come from IP addresses after the -D and they can be replaced with any IP

  4. The last scan we will demonstrate is a scan to determine the OS of the target computer or computers on the subnet In this example we will target the host computer again
  ```
  nmap -sS -O 192.168.2.45
  ```

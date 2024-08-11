# hackers-blog

This is an entire collection of works and resources throughout my cybersecurity journey. 

![Anonymous-Hacker](https://github.com/user-attachments/assets/3c443151-1983-4177-861c-d8e4f720448e)


# Introduction

## **Making a virtual machine**

I started with making a virtual machine using Kali Linux with I learned to be a sufficent OS to use for ethical hacking, cyber security, etc. (Link below) 
- https://www.kali.org/get-kali/#kali-platforms/
  
In the past I have used Virtual Box and Vmware and for this I was thinking of going with VMware Workstation because I am more familiar with it.
I have also found these following resources to teach ethical hacking and cyber security ----

- https://tryhackme.com/
- https://www.hackthissite.org

With further research I also found an image that is ready to use on Vmware. I downloaded the image off of Kali's website then I opened it inside of VMware and set it up. 

# Secure Hacking Enviroment

## **Making the enviroment**

This is a vital step in being able to practice your skills within a secure enviroment using real vulnerable enviroments to target. (Legal? .... maybe)

To build this enviroment first you need a virtual machine which I covered in a previous section. Kali Linux is a good option to start with. 


Once you have your enviroment you need to create and download and enviroment to hack. I found an easy way to do this using Vuln Hub which is a website with
a ton of vulnerable VM's that are waiting to be hacked. 

For this I use Mr. Robot ----

- https://www.vulnhub.com/entry/mr-robot-1,151/

Next I needed to create an isolated network that only works within the two machines. For this I created my own internal network in the settings of the virtual machine manager. You can give your network any name so for this I use "hacknet". 

### **DHCP Server**

As of right now neither of the machines have their own assigned IP address so we need to do that. 

- Navigate to the directory in which you have Virtual Box installed using command prompt in Windows.
- Next you are going to run this command - "vboxmanage dhcpserver add --network=**hacknet** --server-ip=10.38.1.1 --lower-ip=10.38.1.110 --upper-ip=10.38.1.120 --netmask=255.255.255.0 --enable" changing "hacknet" to whatever your internal network is named.
- Finally open up the Kali virtual machine and run **ip address** in terminal and make sure the assigned ip address is either the lower or upper ip that you assigned on windows. 


### **Hacking Mr. Robot**

Here I work on hacking the Mr. Robot virtual machine. AS of right now I can't get into the machine because I do not know the password. 

Now I connect to Mr. Robot ----

- I have to find the machine on the network so I will run " **sudo nmap -sS -T4 10.38.1.110-120** "
- The open ports that come up are 80/tcp and 443/tcp with are both http and https services which tell me they are web servers.
- I opened up my internet browser in Kali and typed the ip address in that I found on the network which was my targets ip.




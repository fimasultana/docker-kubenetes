# Docker-Kubenetes-Lecture01
**Discussion Points on Lecture01:**

1. User space
2. Kernel space
3. Socket Binding
4. Polling
5. Web server
6. Namespace
7. ARP
8. NIC
9. OSI Layer
10. Netcat Server





1. **User Space-** User space is set of locations where normal user processes run. These processes can't access kernel space directly. User space refers to all of the code in an operating system that lives outside of the kernel.


2. **kernel Space-** The kernel provides abstraction for security, hardware, and internal data structures. Role of kernel space is to manage applications/ processes running in user space. Processes running under the kernel has access to all of the memory, whereas the user space have access only to a limited part of memory.

N.B:  Processes running in user space also *don't* have access to the kernel space. User space processes can *only access a small part of the kernel* via an interface exposed by the kernel - the system calls. When a system call is executed the arguments to the call are passed from user space to kernel.



 3. **Socket Binding**- Socket binding is basically assigning an address to it by which, it will be listening for requests to connect to that particular address.
 
 4**. Polling**- Polling is the continuous checking by a controlling device or process of other devices, processes, queues, etc. in some defined sequence to see what state they are in and whether they need attention (such as whether they are still connected, want to communicate, contain tasks to be executed). 
 

5. **Web Server**- A web server is software and hardware that uses HTTP and other protocols to respond to client requests. The basic objective of the web server is to store, process and deliver web pages to the users.


6. **Network Namespace**- A network namespace is a logical copy of the network stack from the host system. ... Each namespace has its own IP addresses, network interfaces, routing tables, and so forth. The default or global namespace is the one in which the host system physical interfaces exist.


7. **ARP**- ARP stands for Address Resolution Protocol. When we try to ping an IP address on our local network, say 192.168.68.106, our system has to turn the IP address 192.168.68.106 into a MAC address. This involves using ARP to resolve the address, hence its name.

  

    Systems keep an ARP look-up table where they store information about what IP addresses are associated with what MAC addresses. When trying to send a packet to an IP address, the system will first consult this table to see if it already knows the MAC address. If there is a value cached, ARP is not used.
    
    If the IP address is not found in the ARP table, the system will then send a broadcast packet to the network using the ARP protocol to ask "who has 192.168.68.106". Because it is a broadcast packet, it is sent to a special MAC address that causes all machines on the network to receive it. Any machine with the requested IP address will reply with an ARP packet that says "I am 192.168.68.106", and this includes the MAC address which can receive packets for that IP.
    
****    - **Arp Table:** In the case where multiple machines have the same IP address, we may get multiple responses. The one that gets placed in the ARP table can vary depending on the networking implementation, how busy hosts are, and how quickly they respond, etc... Once it's in the ARP table, that MAC address is cached and continues to be used until the entry expires or is forcibly cleared. At that point another ARP is done and you may or may not get the same MAC in the ARP table.


    On Linux systems, we can display the ARP table with the command "arp -an". For example:
    
![ARP table](https://paper-attachments.dropbox.com/s_9CC98CDD89DE30EAD1AFEDDFD88AE731DDA7A4F9FCD26FD6CFCBCBC719743BB2_1618657344129_image.png)



    - **ARP Request:** The ARP request message is broadcast on the local area network (Ethernet). All the devices present on the network receive the ARP request message and compare their IP address with the source device's IP address. When the IP address of the source device matched with any of the devices on the local area network, then that device will generate an ARP reply message. If the IP address of the source device does not match with any of the devices present on the local area network, then the devices will automatically drop the packet.The ARP request is broadcast in nature, but the ARP reply is unicast.The need for an ARP request arises when a device wants to know the MAC address of the device to which the source wants to communicate with. It is necessary for both the devices to know each other's both the IP and MAC address.
    
8. **LAN-** LAN stands for local area network. A Network is a group of two or more connected computers, and a LAN is a network contained within a small geographic area, usually within the same building.
9. **CIDR**- CIDR, which stands for Classless Inter-Domain Routing, is an IP addressing scheme that improves the allocation of IP addresses.


10. **MAC Address**- MAC address is the physical address, which uniquely identifies each device on a given network. To make communication between two networked devices, we need two addresses which is MAC address & IP address. It stands for Media Access Control, and also known as Physical address, hardware address, or BIA (Burned In Address).


11. **IP Address**- An Internet Protocol address is known as IP address. IP address specifies the technical format of the addressing and packets scheme. Most networks combine IP with a TCP.
- IPv4: IPv4 was the first version of IP. It is used to identify devices on a network using an addressing system.
- IPv6: It is the most recent version of the Internet Protocol.


12. **NIC**- Netwotk interface Card is a hardware device that is installed on the computer so that it can be connected to the internet. It is also called Ethernet Card or Network Adapter. Every NIC has a 48-bit unique serial number called a MAC address which is stored in ROM carried on the card. Every computer must have at least one NIC if it wants to connect to the internet.


13. **Loopback Interface**- The loopback interface is a virtual interface that is always up and available after it has been configured. Note that the loopback interface is not tied to the address 127.0.0.1. It is used mainly for diagnostics and troubleshooting, and to connect to servers running on the local machine.


![Loopback interface](https://paper-attachments.dropbox.com/s_9CC98CDD89DE30EAD1AFEDDFD88AE731DDA7A4F9FCD26FD6CFCBCBC719743BB2_1618661466981_image.png)



14. **OSI Layer**- The OSI Model is a conceptual framework used to describe the functions of a networking system. The OSI model characterizes computing functions into a universal set of rules and requirements in order to support interoperability between different products and software.

7 layers of OSI model:

![](https://paper-attachments.dropbox.com/s_9CC98CDD89DE30EAD1AFEDDFD88AE731DDA7A4F9FCD26FD6CFCBCBC719743BB2_1618662993094_image.png)

15. **DNS Query**- A DNS query (also known as a DNS request) is a demand for information sent from a user's computer (DNS client) to a DNS server. In most cases a DNS request is sent, to ask for the IP address associated with a domain name. There is some Command line tools for DNS query. Such as, dig, nslookup, host
![](https://paper-attachments.dropbox.com/s_9CC98CDD89DE30EAD1AFEDDFD88AE731DDA7A4F9FCD26FD6CFCBCBC719743BB2_1618662175140_image.png)



![](https://paper-attachments.dropbox.com/s_9CC98CDD89DE30EAD1AFEDDFD88AE731DDA7A4F9FCD26FD6CFCBCBC719743BB2_1618662430930_image.png)

![](https://paper-attachments.dropbox.com/s_9CC98CDD89DE30EAD1AFEDDFD88AE731DDA7A4F9FCD26FD6CFCBCBC719743BB2_1618662514459_image.png)

16. **Netcat webserver**- The Netcat utility program supports a wide range of commands to manage networks and monitor the flow of traffic data between systems.



![netcat server for viewing web request response of localhost:8000 using CLI](https://paper-attachments.dropbox.com/s_9CC98CDD89DE30EAD1AFEDDFD88AE731DDA7A4F9FCD26FD6CFCBCBC719743BB2_1618664223759_image.png)




![Loopback interface listen output](https://paper-attachments.dropbox.com/s_9CC98CDD89DE30EAD1AFEDDFD88AE731DDA7A4F9FCD26FD6CFCBCBC719743BB2_1618664371438_image.png)



![establish netcat Server network to listen on localhost 8000](https://paper-attachments.dropbox.com/s_9CC98CDD89DE30EAD1AFEDDFD88AE731DDA7A4F9FCD26FD6CFCBCBC719743BB2_1618664895604_image.png)



![netcat server to listen on facbook Web reponses](https://paper-attachments.dropbox.com/s_9CC98CDD89DE30EAD1AFEDDFD88AE731DDA7A4F9FCD26FD6CFCBCBC719743BB2_1618667980374_image.png)



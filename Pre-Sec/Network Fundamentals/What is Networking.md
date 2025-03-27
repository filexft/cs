
## What is Networking?


> **"Networking is simple things  connected"**

networks can be found in:
- A city's public transportation system
- Infrastructure such as the national power grid for electricity
- Meeting and greeting your neighbours



In computing, a network can be formed by anywhere from 2 devices to billions.



## What is the Internet?

> "The Internet is <mark style="background: #ADCCFFA6;">one giant network that consists of many, many small networks within itself.</mark>"



The first iteration of the Internet was within the ARPANET project in the late 1960s. funded by the United States Defence Department and was the first documented network in action.

 1989 when the Internet as we know it was invented by Tim Berners-Lee by the creation of the      **W**orld **W**ide **W**eb (**WWW**). 
 It wasn't until this point that the Internet started to be used as a repository for storing and sharing information, just like it is today.

![[internet2 1.png]]

<mark style="background: #ADCCFFA6;">These small networks</mark> are called private networks,
**networks connecting these small networks** are called <mark style="background: #ADCCFFA6;">public networks -- or the Internet!</mark>

So, to recap, a network can be one of two types:  

- A private network  
- A public network


Devices will use a set of labels to identify themselves on a network...


## Identifying Devices on a Network

> To communicate and maintain order, devices must **be both identifying** and **identifiable** on a network. 

What use is it if you don't know whom you're talking to at the end of the day?

like humans devices have two ways to be identified:

- Name  ( **can be** changed if we want )
- fingerprint  ( **can never** be changed )

Every human has an individual set of fingerprints which means that even **if they change their name, there is still an identity behind it.** 

Devices have the same thing: two means of identification, with one being permeable. These are:
- An IP Address
- A Media Access Control (MAC) Address -- think of this as being similar to a serial number.


### IP Addresses  ( Internet Protocol)

> can be used as way of  identifying a host on a network for a <mark style="background: #ADCCFFA6;">period of time</mark> .

where as the IP address **can then associated with another device without the IP address changing.**

IP is a set of numbers that are divided into four octets.
The value of each octet will summarise to be the IP address of the device on the network.
This **number is calculated** through a technique known as **IP addressing** & **subnetting**, 

IP Addresses follow a **set of standards** known as **protocols.**
are the **backbone of networking** and **force many devices** to communicate in the **same language**,
recall that devices can be on both a **private and public** network.


A **public address** is used to **identify the device on the Internet**, 
whereas a **private address** is used to identify a device **amongst other devices**.

|                 |                |                     |
| --------------- | -------------- | ------------------- |
| **Device Name** | **IP Address** | **IP Address Type** |
| DESKTOP-KJE57FD | 192.168.1.77   | Private             |
| DESKTOP-KJE57FD | 86.157.52.21   | Public              |
| CMNatic-PC      | 192.168.1.74   | Private             |
| CMNatic-PC      | 86.157.52.21   | Public              |

These two devices will be able to use their private IP addresses to communicate with each other. However, **any data sent to the Internet** from either of these devices **will be identified by the same public IP address**. 
Public IP addresses are given by your **I**nternet **S**ervice **P**rovider (or **ISP**) at a monthly fee (your bill!)





### MAC Addresses

Devices on a network will all have a <mark style="background: #FFF3A3A6;">physical network interface</mark>, which is a microchip board found on the device's motherboard.

This network interface is assigned a **unique address at the factory** it was built at, called a **MAC** (**M**edia **A**ccess **C**ontrol ) address. 


The MAC address is a **twelve-character**, For example, _a4:c3:f0:85:ac:2d_. 
The first six characters represent the company that made the network interface, and the last six is a unique number.

An interesting thing with MAC addresses is that **they can be faked** or **"spoofed"** in a process known as <mark style="background: #FFF3A3A6;">spoofing</mark>.

 This **Spoofing** occurs when a networked device **pretends to identify as another using its MAC address.**



## Ping (ICMP)


**Ping** uses **ICMP** (**I**nternet **C**ontrol **M**essage **P**rotocol) packets to determine the performance of a connection between devices, for example, if the connection exists or is reliable.

The time taken for ICMP packets travelling between devices is measured by ping, such as in the screenshot below. 
This measuring is done using ICMP's **echo packet** and then ICMP's **echo reply** from the target device.
  

Pings can be performed against devices on a network, such as your home network or resources like websites. The syntax to do a simple ping is `ping IP address or website URL`. Let's see this in action in the screenshot below.















  
## What is the OSI Model?

>  **OSI** model (or **O**pen **S**ystems **I**nterconnection Model)

OSI model is framework dictating **how all networked** devices will **send, receive and interpret data**.

#### Benefits

-  **Main benefit** : devices can have different functions and designs on a network while communicating with other devices.
- Data sent across a network that follows the uniformity of the OSI model can be understood by other devices.



The OSI model consists of **seven layers** which are illustrated in the diagram below. Each layer has a different set of responsibilities and is arranged **from Layer 7 to Layer 1**.


At every individual layer that data travels through, specific processes take place, and **pieces of information are added** to this data, this process is called **Encapsulation.**


## Layer 1 - Physical



- layer references the physical components of the hardware used in networking  
- it's the lowest layer that you will find. 
- Devices use electrical signals to transfer data between each other in a binary numbering system (1's and 0's).



## Layer 2 - Data Link

 
- focuses on the physical addressing of the transmission.
- It receives a packet from the [network layer]([[OSI Model#Layer 3 - Network]]) (including the IP address for the remote computer) and adds in the physical **MAC** (Media Access Control) address **of the receiving endpoint**.
-  Inside every network-enabled computer is a **N**etwork **I**nterface Card (**NIC**) which comes with a unique MAC address to identify it.
- **it’s actually the physical address that is used to identify where exactly to send the information.**



## Layer 3 - Network

>Network layer is **where the magic of routing & re-assembly of data takes place** 
	(from these small chunks to the larger chunk). 

Firstly, routing simply **determines the most optimal path** in which these chunks of **data should be sent**.

these protocols include **OSPF** (**O**pen **S**hortest **P**ath **F**irst) and **RIP** (**R**outing **I**nformation **P**rotocol). 

The factors that decide what route is taken is decided by the following:
- What path is the shortest? I.e. has the least amount of devices that the packet needs to travel across.
- What path is the most reliable? I.e. have packets been lost on that path before?
- Which path has the faster physical connection? I.e. is one path using a copper connection (slower) or a fibre (considerably faster)?

At this layer, everything is dealt with via IP addresses such as 192.168.1.100.

**Devices such as routers capable of delivering packets using IP addresses** are known as **Layer 3 devices** — because they are **capable of working at the third layer** of the OSI model.


## Layer 4 - Transport


plays a vital part in **transmitting data across a network** and can be a little bit difficult to grasp.

When data is sent between devices, it follows one of two different protocols that are decided based upon several factors:
- TCP
- UDP

#### **T**ransmission **C**ontrol **P**rotocol (**TCP**)

- designed with **reliability and guarantee in mind**.
- Incorporates error checking
	- it is how TCP can guarantee that data sent from the small chunks in the session layer (layer 5) has then been received and reassembled in the same order.
- reserves a constant connection between the two devices for the amount of time it takes for the data to be sent and received.

|   |   |
|---|---|
|**Advantages of TCP**|**Disadvantages of TCP  <br>**|
|Guarantees the accuracy of data.|Requires a reliable connection between the two devices. If one small chunk of data is not received, then the entire chunk of data cannot be used.|
|Capable of synchronising two devices to prevent each other from being flooded with data.|A slow connection can bottleneck another device as the connection will be reserved on the receiving computer the whole time.|
|Performs a lot more processes for reliability.|TCP is significantly slower than UDP because more work has to be done by the devices using this protocol.|

TCP is used for situations such as **file sharing, internet browsing or sending an email**. 
This usage is **because these services require the data to be accurate and complete** (no good having half a file!).

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/d47215ad75f503af0b06dacca9ebace6.svg)

  


#### **U**ser **D**atagram **P**rotocol ( **UDP** )

- not nearly as advanced as its brother - the TCP
- doesn't boast the many features offered by TCP, such as error checking and reliability.
- any data that gets sent via UDP is sent to the computer **whether it gets there or not**.
- no synchronisation between the two devices or guarantee; just hope for the best, and fingers crossed.

|                                                                                                                       |                                                                                    |
| --------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **Advantages of UDP**                                                                                                 | **Disadvantages of UDP**                                                           |
| UDP is much faster than TCP.                                                                                          | UDP doesn't care if the data is received.                                          |
| UDP leaves the application layer (user software) to decide if there is any control over how quickly packets are sent. | It is quite flexible to software developers in this sense.                         |
| UDP does not reserve a continuous connection on a device as TCP does.                                                 | This means that unstable connections result in a terrible experience for the user. |



![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/3259184a7fd3dafed265974c31fc8c46.svg)  


UDP is useful in situations where there are small pieces of data being sent. 
For example, protocols used for discovering devices (**_ARP_ and _DHCP_** that we discussed in [Room 2 - Intro to LAN)](https://tryhackme.com/room/introtolan) 
or larger files such as **video streaming** (where it is okay if some part of the video is pixelated. Pixels are just lost pieces of data!)
  

## Layer 5 - Session

Once data has been correctly translated or formatted from the presentation layer (layer 6),  

- this layer begin and maintain a connection to the other computer.
- when a connection is established  -> a session is created, ( connection active == session active)
- it also responsible for closing the connection if not used for a while or lost
- a session _can_ contain "**checkpoints**," where if the data is lost, only the newest pieces of data are required to be sent, saving bandwidth.

 **Sessions are unique** — meaning that data **cannot travel over different sessions**, but in fact, only across each session instead.




## Layer 6 - Presentation

this is the layer in which **standardisation** starts to take place.

Because software developers can develop any software such as an email client differently, the data still needs to be **handled in the same way — no matter how the software works**.

This layer **acts as a translator for data to and from the application layer** (layer 7)



**Security features** such as data encryption (like HTTPS when visiting a secure site) **occur at this layer**.






## Layer 7 - Application



it is the layer in which **protocols and rules are in place** to determine how the user should interact with data sent or received.

 Everyday applications provide a friendly, **G**raphical **U**ser **I**nterface (**GUI**) for users to **interact with data sent or received.**
 
Other protocols include **DNS** (**D**omain **N**ame **S**ystem), which is **how website addresses are translated into IP addresses.**





































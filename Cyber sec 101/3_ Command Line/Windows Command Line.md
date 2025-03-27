
> Learn the essential <mark style="background: #FFF3A3A6;">Windows commands.</mark>



## Introduction

advantages to using a CLI besides speed and efficiency

- **Lower resource usage**: : ex: in cloud computing,
- **Automation**
- **Remote management**: CLI makes it very convenient to use SSH to manage a remote system such as a server, router, or an IoT device. This approach works well on slow network speeds and systems with limited resources.

## Learning Objectives

The purpose of this room is to teach you how to use MS Windows Command Prompt `cmd.exe`, the default command-line interpreter in the Windows environment. We will learn how to use the command line to:

- Display basic system information
- Check and troubleshoot network configuration
- Manage files and folders
- Check running processes

### Important parts

1. Basic System Information
	- we can only issue the commands **within the Windows Path**. 
	- **`set`** to check your path from the command line
	- **`ver`** check window version
	- `systeminfo` command to list various information about the system
	- **`more`** to see data page by page, try  `driverquery`   vs  `driverquery | more`
	- - `help` - Provides help information for a specific command
	- `cls` - Clears the Command Prompt screen.

2. Network Troubleshooting
	 - **`ipconfig`** :  check network info :  IP address, subnet mask, and default gateway.
		 - **`ipconfig /all`** for more information about your network configuration
	
	 - **`tracert`** : which stands for <mark style="background: #FFF3A3A6;">_trace route_</mark>. 
		 - The command `tracert target_name` traces the network route traversed to reach the target.
		 
	 - **`nslookup`** : It looks up a host or domain and returns its IP address
	 - ;
	 - **`netstat`** : displays current network connections and listening ports
		 - **`netstat -abon`** for all, program associated, PID, address numerical form

3. File and Disk Management
	- **`cd`** : It is the equivalent of asking the system, _where am I?_
		- **cd file** or **cd ..**
	- `dir`  to view the child directories
		- - `dir /a` - Displays hidden and system files as well.
		- `dir /s` - Displays files in the current directory and all subdirectories.
	- `tree` to visually represent the child directories and subdirectories.
	- `mkdir directory_name` To create a directory   
		- `rmdir directory_name`To delete a directory, use 
	
	- **`type`**  to easily view text files with the command . 
	- `more` will display a single page 
		- and wait for you to press 
			- `Spacebar` to move by one page (flip the page) or 
			- `Enter` to move by one line.
		- `more file.txt` Display text files
	- `copy` to copy files from one location to another.
		-  `copy *.md C:\Markdown` to refer to multiple files
	- **`move`** to move files 
	- **`del` or `erase`** : to delete a file 

4. Task and Process Management
	- **`tasklist`** to list the running processes using
		- `tasklist /FI "imagename eq sshd.exe"`  filter _image name equals_ `sshd.exe`.
	- **`taskkill /PID target_pid`** can terminate any task 

5. Conculsion / CTF
	- **`shutdown /s`** can shut down a system.
	- **`shutdown /r`** can use to restart a system
	- **`shutdown /a`** use to abort a scheduled system shutdown
## Basic System Information


Before issuing commands, we should **note** that we can only issue the commands **within the Windows Path**.  
You can issue the command **`set`** to check your path from the command line. 


-  **`Path=`** shows the path where MS Windows will execute commands

```shell-session
C:\>set
ALLUSERSPROFILE=C:\ProgramData
[...]
LOGNAME=strategos
NUMBER_OF_PROCESSORS=2
OS=Windows_NT
Path=C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Windows\system32\config\systemprofile\AppData\Local\Microsoft\WindowsApps;C:\Users\strategos\AppData\Local\Microsoft\WindowsApps;
[...]
```


- `ver` command to determine the operating system (OS) version
```shell-session
C:\>ver                                                                                                                                              
Microsoft Windows [Version 10.0.17763.1821]
```


- `systeminfo` command to list various information about the system : OS information, system details, processor and memory

```shell-session
C:\>systeminfo

Host Name:                 WIN-SRV-2019
OS Name:                   Microsoft Windows Server 2019 Datacenter
OS Version:                10.0.17763 N/A Build 17763
OS Manufacturer:           Microsoft Corporation
OS Configuration:          Standalone Server
OS Build Type:             Multiprocessor Free
[...]
```


tips & tricks:

- if the output is too long, you can pipe it through **`more`**
	- Then, you can view it page after page by pressing the space bar button
	- , try running `driverquery` and compare it with running `driverquery | more`





## Network Troubleshooting

The command-line interface provides many networking-related commands to look up your current configuration, check ongoing connections, and troubleshoot networking issues.


#### Network Configuration

You can check your network information using **`ipconfig`**
- to check  IP address, subnet mask, and default gateway.

```shell-session
C:\>ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : eu-west-1.compute.internal
   Link-local IPv6 Address . . . . . : fe80::90df:4861:ba40:f2a8%4
   IPv4 Address. . . . . . . . . . . : 10.10.230.237
   Subnet Mask . . . . . . . . . . . : 255.255.0.0
   Default Gateway . . . . . . . . . : 10.10.0.1
```


- **`ipconfig /all`** for more information about your network configuration

```shell-session
C:\>ipconfig /all

Ethernet adapter Ethernet 3:

   Connection-specific DNS Suffix  . : eu-west-1.compute.internal
   Description . . . . . . . . . . . : Amazon Elastic Network Adapter
   Physical Address. . . . . . . . . : 02-B7-DF-1D-0D-99
   DHCP Enabled. . . . . . . . . . . : Yes
   Autoconfiguration Enabled . . . . : Yes
   Link-local IPv6 Address . . . . . : fe80::90df:4861:ba40:f2a8%4(Preferred) 
   IPv4 Address. . . . . . . . . . . : 10.10.230.237(Preferred) 
   Subnet Mask . . . . . . . . . . . : 255.255.0.0
   Lease Obtained. . . . . . . . . . : Wednesday, May 1, 2024 2:38:05 PM
   Lease Expires . . . . . . . . . . : Wednesday, May 1, 2024 4:08:07 PM
   Default Gateway . . . . . . . . . : 10.10.0.1
   DHCP Server . . . . . . . . . . . : 10.10.0.1
   DHCPv6 IAID . . . . . . . . . . . : 134353458
   DHCPv6 Client DUID. . . . . . . . : 00-01-00-01-27-E3-D1-2B-0E-F8-30-D0-72-3F
   DNS Servers . . . . . . . . . . . : 10.0.0.2
   NetBIOS over Tcpip. . . . . . . . : Enabled
```



####  Network Troubleshooting

-  **`ping target_name`**  : checking if the server can access a particular server on the Internet.
	- we send a **specific ICMP** packet and listen for a response


-  **`tracert`** : which stands for <mark style="background: #FFF3A3A6;">_trace route_</mark>. The command `tracert target_name` traces the network route traversed to reach the target. 
	- it expects the routers on the path to notify us if they drop a packet because its time-to-live (TTL) has reached zero. The terminal output below shows that we passed through 15 routers before reaching our target.

```shell-session
C:\>tracert example.com

Tracing route to example.com [93.184.215.14]
over a maximum of 30 hops:

  1    59 ms    32 ms    42 ms  ec2-3-248-240-3.eu-west-1.compute.amazonaws.com [3.248.240.3]
  2     *        *        *     Request timed out.
  3     *        *        *     Request timed out.
  4     *        *        *     Request timed out.
  5     *        *        *     Request timed out.
  6     *        *        *     Request timed out.
  7     *        *        *     Request timed out.
  8     *        *        *     Request timed out.
  9    <1 ms    13 ms    <1 ms  100.100.2.56
 10    15 ms    11 ms    11 ms  ae-42.a03.londen12.uk.bb.gin.ntt.net [131.103.117.104]
 11    17 ms    11 ms    12 ms  ae-14.r20.londen12.uk.bb.gin.ntt.net [129.250.3.248]
 12    81 ms    80 ms    80 ms  ae-7.r20.nwrknj03.us.bb.gin.ntt.net [129.250.6.147]
 13    83 ms    83 ms    86 ms  ae-0.a02.nycmny17.us.bb.gin.ntt.net [129.250.3.9]
 14    79 ms    79 ms    96 ms  ce-0-3-0.a02.nycmny17.us.ce.gin.ntt.net [128.241.1.14]
 15    81 ms    86 ms    79 ms  ae-67.core1.nyd.edgecastcdn.net [152.195.68.135]
 16    78 ms    78 ms    78 ms  93.184.215.14

Trace complete.
```


####  More Networking Commands



- **`nslookup`** : It looks up a host or domain and returns its IP address
	- One networking command worth knowing
	- The syntax `nslookup example.com` will look up `example.com` using the default name server
	- however, `nslookup example.com 1.1.1.1` will use the name server `one.one.one.one`.

```shell-session
C:\>nslookup example.com
Server:  ip-10-0-0-2.eu-west-1.compute.internal
Address:  10.0.0.2

Non-authoritative answer:
Name:    example.com
Addresses:  2606:2800:21f:cb07:6820:80da:af6b:8b2c
          93.184.215.14

C:>nslookup example.com 1.1.1.1
Server:  one.one.one.one
Address:  1.1.1.1

Non-authoritative answer:
Name:    example.com
Addresses:  2606:2800:21f:cb07:6820:80da:af6b:8b2c
          93.184.215.14
```


- **`netstat`** : displays current network connections and listening ports
	- A basic `netstat` command with no arguments will show you established connections.
		- as shown below. In this case, we only have one SSH connection; we figured out it is SSH because it is bound to port 22.
```shell-session
C:\>netstat

Active Connections

  Proto  Local Address          Foreign Address        State
  TCP    10.10.230.237:22       ip-10-11-81-126:53486  ESTABLISHED
```


- If you are curious about the other options, you can run `netstat -h`, where `-h` displays the help page. We opted for the following options:
	- `-a` displays all established connections and listening ports
	- `-b` shows the program associated with each listening port and established connection
	- `-o` reveals the process ID (PID) associated with the connection
	- `-n` uses a numerical form for addresses and port numbers


We combine these four options and execute the `netstat -abon` command. The result is quite long, but we display the first few lines in the terminal below. It is clear now that the executable `sshd.exe` is responsible for listening for incoming connections on port 22, as shown in the first line. We can also see the process ID (PID) associated with each connection.

```shell-session
C:\>netstat -abon

Active Connections

  Proto  Local Address          Foreign Address        State           PID 
  TCP    0.0.0.0:22             0.0.0.0:0              LISTENING       2116
 [sshd.exe]
  TCP    0.0.0.0:135            0.0.0.0:0              LISTENING       820
  RpcSs 
 [svchost.exe]
[...]
  TCP    0.0.0.0:49669          0.0.0.0:0              LISTENING       2036
 [spoolsv.exe]
  TCP    0.0.0.0:49670          0.0.0.0:0              LISTENING       584 
 Can not obtain ownership information
  TCP    0.0.0.0:49686          0.0.0.0:0              LISTENING       592
 [lsass.exe]
  TCP    10.10.230.237:22       10.11.81.126:53486     ESTABLISHED     2116 
 [sshd.exe]
 [...]
```



## File and Disk Management

####  Working With Directories

-  **`cd`** without parameters to display the current drive and directory. 
	- It is the equivalent of asking the system, _where am I?_
	- `cd target_directory` to change to any directory, equivalent to double-clicking 
	- `cd ..` to go up one level


```shell-session
C:\>cd
C:\

C:\>cd Users

C:\Users>cd 
C:\Users 

C:\Users>cd .. 

C:\>cd 
C:\ 
```

- `dir`  to view the child directories
	- `dir /a` - Displays hidden and system files as well.
	- `dir /s` - Displays files in the current directory and all subdirectories.

```shell-session
C:\Users\strategos>cd
C:\Users\strategos

C:\Users\strategos>dir 
 Volume in drive C has no label. 
 Volume Serial Number is A8A4-C362

 Directory of C:\Users\strategos

05/01/2024  02:40 PM    <DIR>          .
05/01/2024  02:40 PM    <DIR>          ..
11/14/2018  06:56 AM    <DIR>          Desktop
05/01/2024  02:40 PM    <DIR>          Documents
09/15/2018  07:19 AM    <DIR>          Downloads
...
```



- `tree` to visually represent the child directories and subdirectories.
```shell-session
C:\Users\strategos>tree
Folder PATH listing
Volume serial number is A8A4-C362
C:.
├───Desktop
├───Documents
├───Downloads
├───Favorites
├───Links
```



- `mkdir directory_name` To create a directory   
- `rmdir directory_name`To delete a directory, use 

```shell-session
C:\example>mkdir backup_files

strategos@WIN-SRV-2019 C:\example>dir
 Directory of C:\example

05/02/2024  07:36 AM    <DIR>          .
05/02/2024  07:36 AM    <DIR>          ..
05/02/2024  07:36 AM    <DIR>          backup_files
               0 File(s)              0 bytes
               3 Dir(s)  14,984,724,480 bytes free

C:\example>rmdir backup_files

C:\example>dir 
 Directory of C:\example

05/02/2024  07:36 AM    <DIR>          .
05/02/2024  07:36 AM    <DIR>          ..
               0 File(s)              0 bytes
               2 Dir(s)  14,984,724,480 bytes free
```




#### Working With Files


- **`type`**  to easily view text files with the command . 
	- This command will dump the contents of the text file on the screen -
	
-  `more` consider for longer text files.
	- `more` will display a single page and wait for you to press 
		- `Spacebar` to move by one page (flip the page) or 
		- `Enter` to move by one line.

- `copy` allows you to copy files from one location to another.

```shell-session
C:\example>dir
 Directory of C:\example

05/02/2024  08:12 AM    <DIR>          .
05/02/2024  08:12 AM    <DIR>          ..
05/02/2024  07:57 AM                17 test.txt
               1 File(s)             17 bytes
               2 Dir(s)  14,983,409,664 bytes free

C:\example>copy test.txt test2.txt
        1 file(s) copied.

C:\example>dir
 Directory of C:\example

05/02/2024  08:12 AM    <DIR>          .
05/02/2024  08:12 AM    <DIR>          ..
05/02/2024  07:57 AM                17 test.txt
05/02/2024  07:57 AM                17 test2.txt
               2 File(s)             34 bytes
               2 Dir(s)  14,983,409,664 bytes free
```


- **`move`** to move files 
```shell-session
C:\example>dir
 Directory of C:\example

05/02/2024  08:12 AM    <DIR>          .
05/02/2024  08:12 AM    <DIR>          ..
05/02/2024  07:57 AM                17 test.txt
05/02/2024  07:57 AM                17 test2.txt
               2 File(s)             34 bytes
               2 Dir(s)  14,983,409,664 bytes free

C:\example>move test2.txt .. 
        1 file(s) moved. 

C:\example>dir 
 Directory of C:\example

05/02/2024  08:13 AM    <DIR>          .
05/02/2024  08:13 AM    <DIR>          ..
05/02/2024  07:57 AM                17 test.txt
               1 File(s)             17 bytes
               2 Dir(s)  14,983,409,664 bytes free
```

- **`del` or `erase`** : to delete a file 

```shell-session
C:\example>dir
 Directory of C:\example

05/02/2024  08:16 AM    <DIR>          .
05/02/2024  08:16 AM    <DIR>          ..
05/02/2024  07:57 AM                17 test.txt
05/02/2024  07:57 AM                17 test2.txt
               2 File(s)             34 bytes
               2 Dir(s)  14,983,409,664 bytes free

C:\example>erase test2.txt

C:\example>dir 
 Directory of C:\example

05/02/2024  08:16 AM    <DIR>          .
05/02/2024  08:16 AM    <DIR>          ..
05/02/2024  07:57 AM                17 test.txt
               1 File(s)             17 bytes
               2 Dir(s)  14,983,409,664 bytes free
```


We can use the wildcard character `*` to refer to multiple files. For example, `copy *.md C:\Markdown` will copy all files with the extension `md` to the directory `C:\Markdown`.




## Task and Process Management


-  **`tasklist`** to list the running processes using

```shell-session
C:\>tasklist

Image Name                     PID Session Name        Session#    Mem Usage 
========================= ======== ================ =========== ============
System Idle Process              0 Services                   0          8 K
System                           4 Services                   0         88 K
Registry                        84 Services                   0     50,700 K
smss.exe                       276 Services                   0      1,132 K
csrss.exe                      372 Services                   0      5,264 K
wininit.exe                    448 Services                   0      6,892 K
csrss.exe                      456 Console                    1      5,028 K
```
- Let’s say that we want to search for tasks related to `sshd.exe`, 
	- `tasklist /FI "imagename eq sshd.exe"`.
	- Note that `/FI` is used to set the filter _image name equals_ `sshd.exe`.

```shell-session
C:\>tasklist /FI "imagename eq sshd.exe"

Image Name                     PID Session Name        Session#    Mem Usage
========================= ======== ================ =========== ============
sshd.exe                      2116 Services                   0      6,992 K
sshd.exe                      2712 Services                   0      7,668 K
sshd.exe                      4752 Services                   0      7,372 K
```


- **`taskkill /PID target_pid`** can terminate any task 
	- With the process ID (PID) known, 
	- For example, if we want to kill the process with PID `4567`, we would issue the command `taskkill /PID 4567`







## Conclusion

We intentionally omitted a few common commands as we didn’t see a real value for including them in a beginner room. We mention them below so that you know that the command line can be used for other tasks.

- `chkdsk`: checks the file system and disk volumes for errors and bad sectors.
- `driverquery`: displays a list of installed device drivers.
- `sfc /scannow`: scans system files for corruption and repairs them if possible.

In this room, we used the command `more` in two ways:

- Display text files: `more file.txt`
- Pipe long output to view it page by page: `some_command | more`


### CTF 

answers :
- **`shutdown /s`** can shut down a system.
- **`shutdown /r`** can use to restart a system
- **`shutdown /a`** use to abort a scheduled system shutdown
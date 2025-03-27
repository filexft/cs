


## System Configuration ✨

> The **System Configuration** utility (`MSConfig`) is for advanced troubleshooting, and its main purpose is to help diagnose startup issues.

to lunch: search `MSConfig` in search box  

**Note**: You need local administrator rights to open this utility.

The utility has five tabs across the top. Below are the names for each tab. We will briefly cover each tab in this task. 

1. General
2. Boot
3. Services
4. Startup
5. Tools



In the **General** tab, we can select what devices and services for Windows to load upon boot. The options are: **Normal**, **Diagnostic**, or **Selective**. 

In the **Boot** tab, we can define various boot options for the Operating System.

The **Services** tab lists all services configured for the system regardless of their state (running or stopped). A service is a special type of application that runs in the background.

In the **Startup** tab, you won't see anything interesting in the attached VM.  Below is a screenshot of the Startup tab for **MSConfig** from my local machine.

As you can see, Microsoft advises using **Task Manager (**`taskmgr`**)** to manage (enable/disable) startup items. The System Configuration utility is **NOT** a startup management program.


**Note**: If you open Task Manager for the attached VM, you will notice that Task Manager doesn't show a Startup tab.



### CTF 

1. What is the name of the service that lists Systems Internals as the manufacturer?

--- 
the question asking for manufacturer = "Systems Internals", 
so **Psshutdown**

![[Pasted image 20250318153414.png]]


2. Whom is the Windows license registered to?

![[Pasted image 20250318154049.png]]

cliquer sur lunch, et puis, vous trouver le réponse:
**Windows User**

![[Pasted image 20250318154103.png]]



What is the command for Windows Troubleshooting?


le commande est dans le **selected Command**
![[Pasted image 20250318154456.png]]


What command will open the Control Panel? (The answer is  the name of .exe, not the full path)

le commande pour control panel est :

**control.exe**

![[Pasted image 20250318154456.png]]




## Change UAC Settings


You can move the slider to see how the setting will change the UAC settings and Microsoft's stance on the setting.

### CTF
What is the command to open User Account Control Settings? (The answer is the name of the .exe file, not the full path)



![[Pasted image 20250318155016.png]]








## Computer Management

The **Computer Management** (`compmgmt`) utility has three primary sections: System Tools, Storage, and Services and Applications.

![[Pasted image 20250318155432.png]]



#### **Sy-stem Tools**

Let's start with 

###### Task Scheduler ( equivalent to Cron works in linux ).

Per Microsoft, with Task Scheduler, we can create and manage common tasks that our computer will carry out automatically at the times we specify.
To create a basic task, click on **Create Basic Task** under **Actions** (right pane).


###### Event Viewer  ( Equiv Logs / sysLogs in linux ).

to view events that have occurred on the computer.
This information is often used to diagnose problems and investigate actions executed on the system.


Event Viewer has three panes.

1. The pane on the left provides a hierarchical tree listing of the event log providers. (as shown in the image above)
2. The pane in the middle will display a general overview and summary of the events specific to a selected provider.
3. The pane on the right is the actions pane.


There are five types of events that can be logged. Below is a table from [docs.microsoft.com](https://docs.microsoft.com/en-us/windows/win32/eventlog/event-types) providing a brief description for each.

![[five-event-types.png]]



The standard logs are visible under Windows Logs. Below is a table from [docs.microsoft.com](https://docs.microsoft.com/en-us/windows/win32/eventlog/eventlog-key) providing a brief description for each.


![[standard-event-logs.png]]


	

###### Shared Folders

is where you will see a complete list of shares and folders shared that others can connect to.

In the above image, under Shares, are the default share of Windows, C\$, and default remote administration shares created by Windows, such as ADMIN\$. 

As with any object in Windows, you can right-click on a folder to view its properties, such as Permissions (who can access the shared resource). 

Under **Sessions**, you will see a list of users who are currently connected to the shares. In this VM, you won't see anybody connected to the shares.

All the folders and/or files that the connected users access will list under **Open Files**.

###### Local Users and Groups

section you should be familiar with from [Windows Fundamentals 1](https://tryhackme.com/room/windowsfundamentals1xbx) because it's `lusrmgr.msc`.


###### Performance 

you'll see a utility called **Performance Monitor** (`perfmon`).
`Perfmon` is used to view performance data either in real-time or from a log file. This utility is useful for troubleshooting performance issues on a computer system, whether local or remote.

![[Pasted image 20250318171233.png]]

###### Device Manager 

allows us to view and configure the hardware, such as disabling any hardware attached to the computer.

![[Pasted image 20250318171147.png]]







#### **Storage**  

Under Storage is **Windows Server Backup** and **Disk Management**. We'll only look at Disk Management in this room.

**Note**: Since the virtual machine is a Windows Server operating system, there are utilities available that you will typically not see in Windows 10.*

###### Disk Management
Disk Management is a system utility in Windows that enables you to perform advanced storage tasks.  Some tasks are:

- Set up a new drive
- Extend a partition
- Shrink a partition
- Assign or change a drive letter (ex. E:)


#### **Services and Applications**

##### Services

Recall from the previous task; a **service is a special type of application that runs in the background**. Here you can do more than enable and disable a service, such as **view the Properties for the service.** 

##### WMI Control 

configures and controls the Windows Management Instrumentation (WMI) service.

Per Wikipedia, "_WMI allows scripting languages (such as VBScript or Windows PowerShell) to manage Microsoft Windows personal computers and servers, both locally and remotely. Microsoft also provides a command-line interface to WMI called Windows Management Instrumentation Command-line (WMIC)._"

**Note**: The WMIC tool is deprecated in Windows 10, version 21H1. Windows PowerShell supersedes this tool for WMI.




### CTF 

What is the command to open Computer Management? (The answer is the name of the .msc file, not the full path)

> compmgmt.msc

At what time every day is the GoogleUpdateTaskMachineUA task configured to run?



## System Information


We're continuing with Tools that are available through the System Configuration panel.

What is the **System Information** (`msinfo32`) tool?

Per Microsoft, "_Windows includes a tool called Microsoft System Information (Msinfo32.exe).  This tool gathers information about your computer and displays a comprehensive view of your hardware, system components, and software environment, which you can use to diagnose computer issues._"


The  information in **System Summary** is divided into three sections:

- **Hardware Resources**
- **Components**
- **Software Environment**


System Summary will display general technical specifications for the computer, such as processor brand and model.


#####  The information displayed in **Hardware Resources** 
is not for the average computer user. If you want to learn more about this section, refer to the official Microsoft [page](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/hardware-resources#:~:text=Hardware%20resources%20are%20the%20assignable,of%20bus%2Drelative%20memory%20addresses.).


##### Under **Components**, 
you can see specific information about the hardware devices installed on the computer. Some sections don't show any information, but some sections do, such as **Display** and **Input**.

##### In the **Software Environmen**t 
section, you can see information about software baked into the operating system and software you have installed. Other details are visible in this section as well, such as the **Environment Variables** and **Network Connections**.




## Resource Monitor

What is **Resource Monitor** (`resmon`)?

Per Microsoft, "_Resource Monitor displays per-process and aggregate CPU, memory, disk, and network usage information, in addition to providing details about which processes are using individual file handles and modules. Advanced filtering allows users to isolate the data related to one or more processes (either applications or services), start, stop, pause, and resume services, and close unresponsive applications from the user interface. It also includes a process analysis feature that can help identify deadlocked processes and file locking conflicts so that the user can attempt to resolve the conflict instead of closing an application and potentially losing data._"


In the Overview tab, Resmon has four sections:

- **CPU**
- **Disk**
- **Network**
- **Memory**

The same four sections have corresponding tabs across the top. See below.

![[Pasted image 20250319100806.png]]




## Command Prompt



- Let's start with a few simple commands, such as `hostname` and `whoami`.

The command **hostname** will output the computer name.
![](https://assets.tryhackme.com/additional/win-fun2/hostname.png)  

The command **whoami** will output the name of the logged-in user.  
![](https://assets.tryhackme.com/additional/win-fun2/whoami.png)  


some commands that are useful when troubleshooting:
- A command used often is `ipconfig`. This command will show the network address settings for the computer.

- A  command to retrieve the help manual for a command is **`/?`**  ( equivalent to man in linux ) . 

	- For example, to see the help manual for **ipconfig**, you can use the following command: `ipconfig /?`


- **Note**: To clear the command prompt screen, the command is `cls`. 

- The next command is `netstat`. Per the help manual, this command will display protocol statistics and current TCP/IP network connections.


- The `net` command is primarily used to manage network resources. This command supports sub-commands.

	- If you type **net** without a sub-command, the output will show the syntax for the root command showing a few of the sub-commands you can use.

- For the net command, to display the help manual `/?` will not work. In this case, you need to use different syntax, which is `net help`.
	- So, if you wish to see the help information for `net user` , the command is `net help user`.



## Registry Editor

There are various ways to view/edit the registry. One way is to use the **Registry Editor** (`regedit`).

![[Pasted image 20250319102536.png]]



The **Windows Registry** (per Microsoft) is a central hierarchical database used to store information necessary to configure the system for one or more users, applications, and hardware devices.

The registry contains information that Windows continually references during operation, such as:

- Profiles for each user
- Applications installed on the computer and the types of documents that each can create
- Property sheet settings for folders and application icons
- What hardware exists on the system
- The ports that are being used.

**Warning**: The registry is for advanced computer users. Making changes to the registry can affect normal computer operations.




Some of the tools listed in **MSConfig** that weren't mentioned in this room were either covered in Windows Fundamentals 1 or were left for you to explore on your own.



















































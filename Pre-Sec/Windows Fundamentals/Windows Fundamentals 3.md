
## Windows Updates

Windows Update is a service provided by Microsoft to provide security updates, feature enhancements, and patches for the Windows operating system and other Microsoft products, such as Microsoft Defender. 

Updates are typically released on the 2nd Tuesday of each month. This day is called **Patch Tuesday**. That doesn't necessarily mean that a critical update/patch has to wait for the next Patch Tuesday to be released. If the update is urgent, then Microsoft will push the update via the Windows Update service to the Windows devices.

**Tip**: Another way to access Windows Update is from the Run dialog box, or CMD, by running the command `control /name Microsoft.WindowsUpdate`.



## Windows Security

![[Pasted image 20250319111148.png]]


Per Microsoft, "_**Windows Security** is your home to manage the tools that protect your device and your data_".

In case you missed it, **Windows Security** is also available in **Settings**.


In the above image, focus your attention on **Protection areas**.

- **Virus & threat protection**
- **Firewall & network protection**
- **App & browser control**
- **Device security**

![[Pasted image 20250319111209.png]]

status icons:

- **Green** means your device is sufficiently protected, and there aren't any recommended actions.
- **Yellow** means there is a safety recommendation for you to review.
- **Red** is a warning that something needs your immediate attention.

Click on `Open Windows Security`.


## Virus & threat protection

Virus & threat protection is divided into two parts:  

- **Current threats**
- **Virus & threat protection settings**

#### **Current threats**

##### Scan options

- **Quick scan** - Checks folders in your system where threats are commonly found.
- **Full scan** - Checks all files and running programs on your hard disk. This scan could take longer than one hour.
- **Custom scan** - Choose which files and locations you want to check.

#####  Threat history

- **Last scan** - Windows Defender Antivirus automatically scans your device for viruses and other threats to help keep it safe.
- **Quarantined threats** - Quarantined threats have been isolated and prevented from running on your device. They will be periodically removed.
- **Allowed threats** - Allowed threats are items identified as threats, which you allowed to run on your device. 

**Warning**: Allow an item to run that has been identified as a threat only if you are **100%** sure of what you are doing. 


#### **Virus & threat protection settings**


##### **Manage settings** 

- **Real-time protection** - Locates and stops malware from installing or running on your device.
- **Cloud-delivered protection** - Provides increased and faster protection with access to the latest protection data in the cloud.
- **Automatic sample submission** - Send sample files to Microsoft to help protect you and others from potential threats. 
- **Controlled folder access** - Protect files, folders, and memory areas on your device from unauthorized changes by unfriendly applications.
- **Exclusions** - Windows Defender Antivirus won't scan items that you've excluded.
- **Notifications** - Windows Defender Antivirus will send notifications with critical information about the health and security of your device. 

**Warning**: Excluded items could contain threats that make your device vulnerable. Only use this option if you are **100%** sure of what you are doing.   

#####  **Virus & threat protection updates**

- **Check for updates** - Manually check for updates to update Windows Defender Antivirus definitions.  

**Ransomware protection**

- **Controlled folder access** - Ransomware protection requires this feature to be enabled, which in turn requires Real-time protection to be enabled.

**Note**: Real-time protection is turned off in the attached VM to decrease the chances of performance issues. Since the VM can't reach the Internet and there aren't any threats in the VM, this is safe to do. Real-time protection should definitely be enabled in your personal Windows devices unless you have a 3rd party product that provides the same protection. Ensure it's always up-to-date and enabled.  

**Tip**: You can perform on-demand scans on any file/folder by right-clicking the item and selecting 'Scan with Microsoft Defender'.


## Firewall & network protection

What is a **firewall**?

Per Microsoft, "_Traffic flows into and out of devices via what we call ports. A firewall is what controls what is - and more importantly isn't - allowed to pass through those ports. You can think of it like a security guard standing at the door, checking the ID of everything that tries to enter or exit_".

What is the difference between the 3 (**Domain**, **Private**, and **Public**)?

Per Microsoft, "_Windows Firewall offers three firewall profiles: domain, private and public"._

- **Domain** - _The domain profile applies to networks where the host system can authenticate to a domain controller._ 
- **Private** - _The private profile is a user-assigned profile and is used to designate private or home networks._
- **Public** - _The default profile is the public profile, used to designate public networks such as Wi-Fi hotspots at coffee shops, airports, and other locations._

![[Pasted image 20250319112244.png]]

If you click on any firewall profile, another screen will appear with two options: **turn the firewall on/off** and **block all incoming connections**.


![[Pasted image 20250319112006.png]]
**Warning**: Unless you are **100%** confident in what you are doing, it is recommended that you leave your Windows Defender Firewall enabled.

You can view what the current settings for any firewall profile are. In the above image, several apps have access in the Private and/or Public firewall profile. Some of the apps will provide additional information if it's available via the `Details` button.


![[Pasted image 20250319112441.png]]




## App & browser control


In this section, you can change the settings for the **Microsoft Defender SmartScreen**.

Per Microsoft, "_Microsoft Defender SmartScreen protects against phishing or malware websites and applications, and the downloading of potentially malicious files_".

Refer to the official Microsoft document for more information on Microsoft Defender SmartScreen [here](https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).

![[Pasted image 20250319112730.png]]

**Check apps and files**

- **Windows Defender SmartScreen** helps protect your device by checking for unrecognized apps and files from the web. 

![](https://assets.tryhackme.com/additional/win-fun3/windows-smartscreen.png)  

**Exploit protection**

- Exploit protection is built into Windows 10 (and, in our case, Windows Server 2019) to help protect your device against attacks.

**Warning**: Unless you are 100% confident in what you are doing, it is recommended that you leave the default settings.


## Device security




Even though you'll probably never change any of these settings, for completion's sake, it will be covered briefly.

![](https://assets.tryhackme.com/additional/win-fun3/windows-device-sec.png)  

**Core isolation**

- **Memory Integrity** - Prevents attacks from inserting malicious code into high-security processes.

![](https://assets.tryhackme.com/additional/win-fun3/windows-mem-integrity2.png)  

Warning: Unless you are 100% confident in what you are doing, it is recommended that you leave the default settings.   

The below images are from another machine to show another security feature that should be available in a personal Windows 10 device.  

Security processor  

![](https://assets.tryhackme.com/additional/win-fun3/windows-sec-processor.png)  

Below are the **Security processor details**.

![](https://assets.tryhackme.com/additional/win-fun3/windows-tpm.png)  

What is the **Trusted Platform Module** (**TPM**)?  

Per Microsoft, "_Trusted Platform Module (TPM) technology is designed to provide hardware-based, security-related functions. A TPM chip is a secure crypto-processor that is designed to carry out cryptographic operations. The chip includes multiple physical security mechanisms to make it tamper-resistant, and malicious software is unable to tamper with the security functions of the TPM_".


## BitLocker

What is **BitLocker**?

Per Microsoft, "_BitLocker Drive Encryption is a data protection feature that integrates with the operating system and addresses the threats of data theft or exposure from lost, stolen, or inappropriately decommissioned computers_".

On devices with TPM installed, BitLocker offers the best protection.

Per Microsoft, "_BitLocker provides the most protection when used with a Trusted Platform Module (TPM) version 1.2 or later. The TPM is a hardware component installed in many newer computers by the computer manufacturers. It works with BitLocker to help protect user data and to ensure that a computer has not been tampered with while the system was offline_".

Refer to the official Microsoft documentation to learn more about BitLocker [here](https://docs.microsoft.com/en-us/windows/security/information-protection/bitlocker/bitlocker-overview).
- BitLocker provides maximum protection when used with a Trusted Platform Module (TPM), which is a common hardware component installed on Windows devices. The TPM works with BitLocker to ensure that a device hasn't been tampered with while the system is offline.

- In _addition_ to the TPM, BitLocker can lock the normal startup process until the user supplies a personal identification number (PIN) or inserts a removable device that contains a _startup key_.



## Volume Shadow Copy Service

Per [Microsoft](https://docs.microsoft.com/en-us/windows-server/storage/file-server/volume-shadow-copy-service), the Volume Shadow Copy Service (VSS) coordinates the required actions to create a consistent shadow copy (also known as a snapshot or a point-in-time copy) of the data that is to be backed up. 

Volume Shadow Copies are stored on the System Volume Information folder on each drive that has protection enabled.  

If VSS is enabled (**System Protection** turned on), you can perform the following tasks from within **advanced system settings**. 

- **Create a restore point**
- **Perform system restore**
- **Configure restore settings**
- **Delete restore points**

From a security perspective, malware writers know of this Windows feature and write code in their malware to look for these files and delete them. Doing so makes it impossible to recover from a ransomware attack unless you have an offline/off-site backup.

If you wish to configure Shadow Copies within the attached VM, see below.

![](https://assets.tryhackme.com/additional/win-fun3/vss1.png)  

![](https://assets.tryhackme.com/additional/win-fun3/vss2.png)

**Bonus**: If you wish to interact hands-on with VSS, I suggest exploring Day 23 of [Advent of Cyber 2](https://tryhackme.com/room/adventofcyber2).



























































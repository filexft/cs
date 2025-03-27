
## Introduction

## Learning Objectives

This is the second room in the [Command Line](https://tryhackme.com/module/command-line) module. It is an introductory room to PowerShell, the second—only historically—command-line utility built for the Windows operating system.

- Learn what PowerShell is and its capabilities.
- Understand the basic structure of PowerShell’s language.
- Learn and run some basic PowerShell commands.
- Understand PowerShell’s many applications in the cyber security industry.

### Important Notes




## What Is PowerShell

From the official Microsoft [page](https://learn.microsoft.com/en-us/powershell/scripting/overview?view=powershell-7.4): 
>_“PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework.”_

-  It combines a command-line interface and a scripting language built on the .NET framework
- **PowerShell is object-oriented**
- PowerShell has lately expanded to support macOS and Linux


#### A Brief History of PowerShell

PowerShell was developed to overcome the limitations of existing command-line tools and scripting environments in Windows.

- In the early 2000s, as Windows was increasingly used in complex enterprise environments, traditional tools like `cmd.exe` and batch files fell short in automating and managing these systems. Microsoft needed a tool that could handle more sophisticated administrative tasks and interact with Windows’ modern APIs.

Jeffrey Snover, a Microsoft engineer, realised that Windows and Unix handled system operations differently—Windows used structured data and APIs, while Unix treated everything as text files. 

- This difference made porting Unix tools to Windows impractical. Snover’s solution was to **develop an object-oriented approach**, combining scripting simplicity with the power of the .NET framework. 

- Released in 2006, PowerShell allowed administrators to automate tasks more **effectively by manipulating objects**, offering deeper integration with Windows systems.

As IT environments evolved to include various operating systems, the need for a versatile automation tool grew. In 2016, Microsoft responded by releasing **PowerShell Core**, 
- an open-source and cross-platform version that runs on Windows, macOS, and Linux.

#### The Power in PowerShell

> To fully grasp the power of PowerShell, we first need to understand what an **object** is in this context.


In programming, an **object** represents an item with **properties** (characteristics) and **methods** (actions). For example, a `car` object might have properties like `Color`, `Model`, and `FuelLevel`, and methods like `Drive()`, `HonkHorn()`, and `Refuel()`.

Similarly, in PowerShell, objects are fundamental units that encapsulate data and functionality, making it easier to manage and manipulate information. An object in PowerShell can contain file names, usernames or sizes as data (**properties**), and carry functions (**methods**) such as copying a file or stopping a process.

The traditional Command Shell’s basic commands are text-based, meaning they process and output data as plain text. Instead, when a **cmdlet** (pronounced _command-let_) is run in PowerShell, it returns objects that retain their properties and methods. This allows for more powerful and flexible data manipulation since these objects do not require additional parsing of text.


## PowerShell Basics
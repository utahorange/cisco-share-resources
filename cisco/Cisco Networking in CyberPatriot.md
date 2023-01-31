Dedicated to all those who supported me along the way, you know who you are.

# Introduction

## Preface

Hello, I am a current high school junior that has specialized in Cisco Networking for the past 4 years. Over time, I’ve found that it's hard to get started in this particular field of information security.

  

I created this document to put down in writing what I have gleaned in my experience. It does not aim to cover networking content whatsoever, but is instead a summary of strategies that I found to be useful in learning networking.

  

## What is Cisco

Cisco is the name of a company that creates networking devices such as routers, switches, and firewalls. They are not that prevalent nowadays in home networks, but are still a major player in the industry. Many CyberPatriot competitors colloquially refer to the networking aspect of the competition as Cisco. Configuration and theory concepts learned on Cisco devices transfer to networking in general.

  

## Why should you do Cisco

Cisco is, in my opinion, the easiest specialty out of Windows and Linux to master, especially in regards to CyberPatriot competition scores. It is however the most intimidating, hardest to get started,  and possibly the most uninteresting, at first. It is because of these facts that it is much easier to get onto good teams by specializing in Cisco than with Windows or Linux. It is also the easiest to get certifications with.

  

Getting Started

Getting started in Cisco is easy. Simply do the following:

1.  Have your coach add you to the competition Netacad course.
    
2.  Download Packet Tracer (link is under resources in the Netacad course).
    

# Mastering Theory

This is painful and there’s no way to get around it. You just simply have to put in time to read and hold yourself to knowing the content. The actual content tested during competition is limited to only the modules specified, which skips many chapters of the multiple textbooks used in the curriculum. There is also content relevant only to Cisco-proprietary devices, which can sometimes be ignored.

  

## How the Curriculum is Organized

Netacad is organized into sections known as modules, which generally skip around chapters in a few different textbooks (CCNA Security, ITN Fundamentals, CCNA SRWE, etc…).

  

## How to Study Long-term

Having a study schedule is useful, but holding yourself to it is the difficult part. I found it easiest to simply progress on modules whenever I had the time, whether that be in class or over the weekends. I had a spreadsheet with all the tested modules that I would record how far I progressed. You really only need to learn up to the modules tested at each round of the competition.

  

## How to Prep for Competition Cisco Quizzes

It is best to have read through all of the associated modules before semifinals or the round before Nationals. If not, familiarize yourself with generally where certain topics are in the textbooks. Most Cisco questions can be done with only Google or searching through Netacad without significant studying. However, application questions do show up, especially in Round 2 and Round 3.

  

## Types of Questions

There are three major types of questions:

1.  Straight theory/vocabulary - google it/search in NetAcad (sometimes taken from publicly available CCNA tests).
    
2.  Commands - usually can google or NetAcad, might need some configuration knowledge.
    
3.  Conceptual Application - most difficult kind of question, usually appears as a topology describing the behavior of protocols or packets.
    

  

# Mastering Configuration

## CLI Basics

### Miscellaneous

The ! key signifies a shortcut.

### Moving Around - Privilege Modes and Lines

Cisco operates on the principle of privilege modes. This is essentially the Cisco equivalent of sudo privileges in Linux and administrator privileges in Windows.

  

Device_Name> ! This is known as user exec. Moving to the next level generally requires a password.

Device_Name# ! This is known as privileged exec.

Device_Name(config)# ! This is known as global configuration mode.

  

enable

configure terminal

exit

end

  

There are also the Console, VTY, and Auxiliary lines. The most important is the Console line. In real life, you cannot simply click on a router and magically access its CLI. You need a console cable and monitor (not including peripherals) to at least view the CLI. That is the purpose of remote access protocols such as SSH and Telnet, which allow you to connect through the console cable to configure a device. SSH and Telnet are not automatically configured on a network device, so you’re most likely using PuTTY when it is first booting up, but the point is the same.

### Saving your work

There’s really two kinds of saving. One is saving your packet tracer file. The other way is saving running device configuration to startup configuration (‘copy run start’ or ‘copy running-config startup-config’). Both should be done consistently. 'copy run start' can also be written as 'do write’ (shortened to 'do wr'). When you make changes in a device by typing in commands, you change the running configuration file. However, the running configuration file is stored in RAM (random access memory), which is volatile, meaning it will be overwritten/lost if you power down/restart your device. Thus, you need to save your changes to the startup configuration file which is stored in NVRAM. This is the file that the device uses to boot when first powered on. 

  

## CLI Shortcuts to learn

The whole point of shortcuts is to be faster. Cisco IOS CLI offers a surprising amount of shortcuts that aren’t entirely straightforward, but are extremely important long-term. 

  

Note that the CLI is not case-sensitive except for passwords and names of things. The CLI works by recognizing what command you are attempting to type. It checks this by letter. This means that many commands can be shortened to its shortest but still unique form. For example “router ospf” can be shortened to “ro o” in most cases. 

-   if in the user exec mode, you get stuck in it trying to translate your mistyped command to a web address, use CTRL-SHIFT-6 (escape sequence)
    

-   this can also be used for ending pings on network devices
    

-   up/down arrow keys for command history
    
-   the full list of show commands can be seen with “show ?”
    
-   commands are not case-sensitive
    
-   Commands completed with the tab button are equivalent to their shortened versions
    
-   "do..." commands can be entered anywhere
    
-   Ctrl+a to go to beginning of line
    
-   Ctrl+e to go to end of line
    

  

Logs often interrupt your work. One particularly nasty kind of log is the OSPF adjacency change message. You can disable them with the command “no log-adjacency-changes”.

  

One highly recommended strategy is to compile notepad scripts and use them during competition. I highly recommend scripting basic device security and VPN before competition. ACL configurations cannot really be pre-scripted but should still be done on notepad to facilitate changes.

  

Ease of Use

-   Use the "Fast Forward Time" button if there are orange dots on the topography or if a process is loading on the command line
    
-   To figure out which interface connects 2 devices, you can use process of elimination (turn off interfaces one by one)
    

  

Devices

-   If asked to continue with configuration dialogue when opening a device, type no
    
-   All router ports are by default off, all switch ports are by default on
    
-   Serial ports must be manually added to most routers by turning the router off using the "Physical" tab and then dragging the serial port into the slot from the bottom.
    
-   To turn a device on, Physical Device View-> zoom in -> switch to power on and off (grey = off, yellow = on)
    
-   PC ethernet ports can be turned off (but never seen this in competition before)
    
-   Pings in end devices work in the command prompt under desktop, while pings for network devices work in Privileged Exec and on interface configurations.
    

  

## Troubleshooting

This is the most mentally-challenging aspect of Cisco. There are simply too many moving parts in your normal network, of which any could be contributing to a connectivity error. However, there are still strategies in troubleshooting for speed and accuracy.

### Connectivity

This is probably the most common problem.

1. basic stuff

- default gateway not configured

- L2/L3 port not on

- DNS not configured correctly

- does not have an IP

- timeout (spam ping or change ping TTL)

- pinged private IP not on network, dropped by router

- ARP problem (extremely rare)

2. VLAN

-  trying to ping dif VLAN

- wrong default gateway on VLAN

- native VLAN mismatch

- trunk not configured

- VLAN not allowed on trunk

3. routing

- default/static route goes somewhere weird

- wrong/no network commands in dynamic routing

4. security

- ACL rules

### VLANs

-   PCs not connected to right ports (reconnect it)
    
-   Native VLAN mismatch
    

VPNs

-   different SA settings (check )
    

  

Most Used Show Commands

-   show run
    
-   show ip int brief
    
-   show vl brief
    
-   show dhcp binding
    

# Cisco Competition Strategies

## Quiz

Before your 6-hour window starts, it is helpful to have all the relevant Netacad textbooks open on your personal account. 

  

## Packet Tracer

### With two people

Being familiar with using notepad scripts is extremely beneficial. You can either have the second person shadow your commands and check if you make a mistake, or you can have them work on scripting later configurations specified in the readme. Personally, I prefer the second strategy because the first is extremely boring and tedious. Both of you should be familiar with where you store your scripts and equally capable network administrators.

# Beyond CyberPatriot

If you have spent a significant amount of time studying for the competition, I highly recommend you capitalize on that time and invest in a certification to prove to the world you did not waste those high school years. There are a few certifications that can be pursued, which include but are not limited to the following:

-   CCNA
    
-   CompTIA Security+
    
-   CompTIA Networking+
    

# Resources

Most Helpful

  

YouTube

Practice Questions

Miscellaneous

[Widget](https://forge.kmi.open.ac.uk/pt/app/default.html#/session-unavailable)

  
**
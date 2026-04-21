---
title: Chapter 2 - Note
date: 2026-04-21 00:00:00 +0000
categories: [Practical-Malware-Analysis, Chapter-2]
tags: [Malware-analysis, Introduction]
---

# Malware Analysis in virtual machines

in malware analysis running malware on real system could have potential impact as it can damage other system in the environment. Because of that malware analyst use virtual machine to mimic the real machine and using snapshot to revert back to the original analyst machine. But some complicated and sophisticated malwares behave differently in VMs to thwart analysis. for that analyst run such malwares in physical system with norton ghost to manage backup /assets/img/notes/PMA/Ch2/images of OSs

## structure of VM

![alt text](/assets/img/notes/PMA/Ch2/image39.png)

This book prefer to use VMware but i am going to use virtual box. this are the application which provides desktop virutalization and snapshot features.

## creating malware analysis machine

just download win 10 and set it up with max resources according to your machine i have given 6 cores, 16 GB ram and 80gb storage space

## cofiguring VBox

we can not disconnect the newwork if we do so than we cannot find the network signature of that malware
setting up Host-Only network creates a separate private LAN between host OS and guest OS, this setting most people use.

recommanded netwrok setting is to set that up on host-only, creating shared folder when to share files and taking snapshots as needed

But malware authors have found exploits against all of that shared folder and drag-and-drop features. so it is best practice not to do that when running malware in Vbox

VMware has record/reply feature which gives us ability to reply CPU instructions.

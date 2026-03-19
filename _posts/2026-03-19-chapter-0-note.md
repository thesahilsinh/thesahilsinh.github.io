---
title: Chapter 0 - Note
date: 2026-03-19 00:00:00 +0000
categories: [Practical-Malware-Analysis, Chapter-0]
tags: [Malware-analysis, Introduction]
---

# Chapter 0 – Introduction

### Goal of malware analysis:

- network intrusion
- determine what a specific binary can do, how to detect it, and how to measure and contain its damage.
- host-based and network signature
    - **host-based** : used to detect malware on endpoint or host
    - **network** : used to detect malware by monitoring network traffic. this can be created without analyzing malware analysis.

### Malware analysis techniques:

- **Basic Static analysis**: examining binary without viewing instructions(assembly). this process is quick.
- **Basic Dynamic analysis**: Just run the malware and enjoy watching the destruction :D in a virtualized or sandbox environment. I would do that in my friends' PC :)
- **Advanced Static analysis**: complex analysis where most people quit. basically reverse-engineering malware's internals using disassembler and look at the program instructions in order to discover the behavior of program. Simply without running malware on your friends PC knowing what this malware is capable of. 
- **Advanced Dynamic analysis**: we use debugger to examine internal state of a running malicious binary. in other term we run the malware without letting it to destroy anything. How COOL right !

### Types of malware:

Backdoor, botnet, downloader, information-stealing, launcher, rootkit, scareware, spam-sending, worm-virus

I am not going to describe this i just know this terms. Also there are many more which is not in this book.

### General Rules:

1) Don't go into too deep. just try to get overview and look what's happening   
2) try different angle, or just try different approach (like kinda you treat your girl)   
3) it is like cat-mouse game mouse is malware authors and we are cat.  
 

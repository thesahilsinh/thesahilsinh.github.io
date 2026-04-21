---
title: Chapter 1 - Note
date: 2026-04-21 00:00:00 +0000
categories: [Practical-Malware-Analysis, Chapter-1]
tags: [Malware-analysis, Introduction]
---

# Chapter 1 - Basic Static Analysis

This chapter is about Basic Static analysis of Malware.

what i have learned in this chapter by doing labs and going through the lessons.

- in static we analyze code or structure of malware where in dynamic we run the malware.

three ways to extract information.

- using antivirus tools to confirm maliciousness.
- using hashes to indetify malware.
- gleaning info from file's strings, functions, and headers

### Antivirus scanning

- we basically use virustotal for this

### hashing: fingerprint of malware

- many algos are there majorly used is MD5 and SHA versions

### Strings:

- explanation of ASCII and UNICODE syntax and how null terminator is used in both
- we use command called strings followed by program. eg strings sahil.malware

### packed and obfuscated malware

- obfuscated malware are the ones whose execution has attempted to hide and packed is subset of obfuscated malware and it compressed so that this both technique make malware to possibly identified by static analysis
- to detect packer we use TOOl called PEiD. use to detect packer or compiler employed.

### portable executable file format:

- using file type we can know that it is made for what like PE is for windows, ELF linux and mach-o or .app for macos

### linked libraries and functions:

- imports: functions used by one program that are actually stored in a different program. like code libraries
- code libraries can be connected to main executable by linking.

### static, runtime, and Dynamic Linking

- static : common in UNIX system. this linking increase file size as it does not refer or point to any function and rely on system, as it load all code from that library in able to run so it increase the size of the program and it make our job harder to differentiate executable's own code and file contains linked code.

- runtime : commanly used in malware, as it uses the function as needed not at program start, as with dynamically linked programs. some windows functions allow programmers to import linked functions not listed in file header. like LoadLibrary and getProcAddress allow a program to access any function in any library on the system. 

- dynamic linking : when functions are called that functions executes within the library. the most common and interesting for analysts.

    - for this we use TOOL called Dependency Walker

- imported functions : info about specific functions used by an EXE.
- Exported Functions : 
    - Usually only interesting in DLLs (not EXEs)  
    - Malware sometimes exports functions to act as a dropper or loader

### Static analysis in practice :

![alt text](/assets/img/notes/PMA/Ch1/image.png)   

If you have no idea what do a specific functions/API do look into windows official MSDN website.

Kernel32.dll = can open and manipulate processes
- OpenProcess, GetCurrentProcess, GetProcessHeap and files --> ReadFile, CreateFile, and WriteFile

User32.dll = it runs GUI and not necessarily displayed
- RegisterClassEx, SetWindowText, ShowWindow

This Ex at the end of the function name denotes the version updation. A or W is for string parameter one for ASCII and wide char.

SetwindowsHookEx --> used in spyware, Keylogging functionality.
RegisterHotKey --> registers hotkey like ctl + alt + del

GDI32.dll = graphics-related and program has GUI

shell32.dll = one program can launch other program

Advapi32.dll = program is using registry (look like directory). if this dll is available than we should look for the registry key.

this above information we can gathered is just because of it is not packed. let me show you how packed malware or program's import and export looks like.

![alt text](/assets/img/notes/PMA/Ch1/image-1.png)   

simple hello world program has more imports and exports details than this. so this indicates that it is a packed using packer.

### PE file headers and sections

Sections in PE File:

- **.text** : contains instructions that CPU executes. the only section that can execute and should be only section that include code.

- **.rdata** : contains import and export information. we see the same info using Dependency walker and PEview. this also stores other read-only data. sometime file contains .idata and .edata for import and export

- **.rsrc** : include resources used by exe that are not part of executable, icons, img, menus, strings. strings can be stored in .rsrc or main program. often stored in .rsrc

![alt text](/assets/img/notes/PMA/Ch1/image-2.png)

now later in the chapter it shows how we can see the resource section of the program using the TOOL resource hacker

other TOOLs for browsing PE Header
- PEBrowse Professional - Free and allow us to look at BYTE level
- PE Explorer - rich GUI but paid

### PE Header summary

some info that we can get from PE header which contains metadata

![alt text](/assets/img/notes/PMA/Ch1/image-3.png)

Conclusion:

virustotal
strings
packer
PE Header
dependancy

this gives the overall idea of what the program can do.

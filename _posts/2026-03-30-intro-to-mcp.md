---
title: "Introduction to Model Context Protocol (MCP) – ANTHROPIC"
date: 2026-03-30 12:00:00 +0000
categories: [AI, MCP, Anthropic]
tags: [mcp, claude, anthropic, tools, ai-agents, python]
---

# Introduction :    

### Goals :  

- overview  
- MCP clients and servers  
- Tools  
- resources    
- prompts   

### requirement :    

- basic python and UV setup   

powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"   

i am using this command to install in my win pc    

https://docs.astral.sh/uv/     

for good understanding of UV use this website    

### MCP :   

you can see the notes after the video but here i will summurize in my own words and what i understood is that MCP help us to connect a tool using API function calls and help us to lower down the burdon of making schemas + functions which help to perform task on it own.

official defination : Model Context Protocol (MCP) is a communication layer that provides Claude with context and tools without requiring you to write a bunch of tedious integration code. Think of it as a way to shift the burden of tool definitions and execution away from your server to specialized MCP servers.

this one i have cited from the course it self just for reference.

### MCP CLients :    

this bridge our server with MCp server.   
it has two protocol that a client can communicate to server.
- Standard IO : locally running mcp server
- Websockets : it runs functions depends on the request.

# Hands-on with MCP servers

### Project setup

CLI based chatbot :   

so to set up a CLI chatbot download the zip files that are in my repository called cli_project. this files are the part of this course and i am performing the things and setup described in course.

### defining tools with MCP

in here we define the tools in our MCP server and for that anthropic has come up with a good python SDK to setting up MCP server

from mcp.server.fastmcp import FastMCP

mcp = FastMCP("DocumentMCP", log_level="ERROR")

This SDK is so good at generating json schemas which can understand to claude just using field descriptions.

Key Benefits of the SDK Approach
- No manual JSON schema writing required
- Type hints provide automatic validation
- Clear parameter descriptions help Claude understand tool usage
- Error handling integrates naturally with Python exceptions
- Tool registration happens automatically through decorators

### server inspector

so when we run the mcp_server.py file it looks like this

![alt text](image.png)

# Connecting with MCP Clients

### implementing a client

client has two main components :   
- MCP client - custom class we create to make using session easier
- client session - actual connection to server

so when we run this command "uv run mcp_client.py" it connects to server and we can now call the functions that are described in that clients' class using main.py application

### defining resources

it is feature like mentioning username but here we are taking about the resource that a client can request upon and to mention those resource we use "@" symbol.

two types :

- Direct : URI doesn't contain any params.
- Templated : URI contains one or more params. SDK parses these and passes them as args to our function.

### accessing resources

![alt text](image-1.png)

like this

### Defining prompts 

we can define it in our prompt like formate .md as a markdown and claude model will do the job for use but this functionality makes the users job very easy to write less prompt. so we can define a common prompts and makes user's job very easy to perform some common task.

for this we use this code :

@mcp.prompt()

### prompts in the client

![alt text](image-2.png)


# Assessment and wrap up

![alt text](image-3.png)

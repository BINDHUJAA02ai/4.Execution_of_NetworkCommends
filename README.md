# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR

## Program:
 **PING COMMAND**
 Client
 ```
  
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
Server:
``` 
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
**TRACEROUTE COMMAND**
 ``` 
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output
## PING COMMAND 
 client:
 ![Screenshot 2025-04-17 142736](https://github.com/user-attachments/assets/e182c4c3-f4d0-455b-abe2-77b414cb7192)

 server:
 ![Screenshot 2025-04-17 142717](https://github.com/user-attachments/assets/5c2fb8c4-8657-40b6-b152-710fa92d420e)
 
##  TRACEROUTE COMMAND
![Screenshot 2025-04-17 143352](https://github.com/user-attachments/assets/842a756a-4999-46e3-aa34-8a2bfe531d5a)

 
## Result
Thus Execution of Network commands Performed 

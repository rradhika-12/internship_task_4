# internship_task_4

## Task 4 : Setup and Use a Firewall on Windows/Linux
### Objective: Configure and test basic firewall rules to allow or block traffic.
## TOOLS USED: 
    FOR WINDOWS: WINDOWS DEFENDER FIREWALL (WITH ADVANCED SECURITY) 
    FOR LINUX: UFW (UNCOMPLICATED FIREWALL) 
### Deliverables: Screenshot/configuration file showing firewall rules applied.

    1.Open firewall configuration tool (Windows Firewall or terminal for UFW).
    2.List current firewall rules.
    3.Add a rule to block inbound traffic on a specific port (e.g., 23 for Telnet).
    4.Test the rule by attempting to connect to that port locally or remotely.
    5.Add rule to allow SSH (port 22) if on Linux.
    6.Remove the test block rule to restore original state.
    7.Document commands or GUI steps used.
    8.Summarize how firewall filters traffic.

    ### Outcome: Basic firewall management skills and understanding of network traffic filtering.

## Port 23 is used by the Telnet protocol, which enables remote connections to a computer. But here’s the problem: 

      Telnet is unencrypted → anything typed (username, password, commands) is sent in plain text over the network. 
    Attackers can sniff this data using tools like Wireshark or tcpdump. 
    Hackers target port 23 in port scans looking for open Telnet services, especially on older or misconfigured devices (routers, IoT devices, Linux servers). 
    In modern security, Telnet is considered unsafe, and SSH (port 22) is used instead for remote access because it's encrypted. 

## What Happens After Blocking Inbound Port 23? 
Once you apply this rule in Windows Firewall or UFW: 
   
    Any external device trying to connect to your system over port 23 (e.g., using a Telnet client) will be denied. 
    If a Telnet server is running on your system, nobody will be able to reach it from outside. 
    This does not affect internal applications that don’t use that port. 
    If someone runs a port scan against your machine, port 23 will appear as closed or filtered, making it invisible or unreachable. 
## Why It Matters for Cybersecurity: 
    Blocking unused and risky ports like 23 (Telnet) reduces your attack surface. 
    It's part of a "default-deny" security model, where you only open what is needed. 
    Even if Telnet is not running, blocking the port prevents future vulnerabilities if someone accidentally enables it. 

### After blocking port 23, you stop any remote Telnet attempts to your machine, securing it from a legacy and insecure protocol. This is a proactive firewall rule used in real-world system hardening. 

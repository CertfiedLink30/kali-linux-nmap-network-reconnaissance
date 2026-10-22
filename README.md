# kali-linux-nmap-network-reconnaissance
Beginner Nmap Network Scanning Lab
  Project Overview
  This project shows my first steps using Kali Linux and Nmap to check which network ports are open or closed 
  I completed this work in  a safe local virtual lab using my own computer.  The goal was to practice basic network scanning, identifying a running service, and Nmap reports network services, and record what I found. 
  Objective: Check selected TCP ports, see whether they were open or closed, and learn how Nmap reports network services.

Lab Environment
  - Operating system: Kali Linux 2026.2
  - Virtualization: Oracle VirtualBox
  - Scanning Tool: Nmap 7.99
  - Target 127.0.0.1 (localhost)
  - Test Service: Python HTTP server
  - Environment: Local and authorized cybersecurity lab.
What I Executed
  Phase 1: Basic Port Scan
    First I scanned three common ports using this command: nmap -sT -sV -p 22,80,443 127.0.0.1
  The options used in this command were
    - -sT: Performs a basic TCP connection scan.
    - -sV: Attempts to identify the services and version.
    - -p 22,80,443: Scans only ports 22, 80, and 443.
    - 127.0.0.1: Scans my own computer also known as localhost
Results:
      After a couple of syntax errors I confirmed that all three ports were closed during the initial scan.  This meant that no service was accepting connections on those particularly ports at that time.

  Phase 2: Start a Test Web Server
   - Next, I started a temporary Python web server on port 8080.  I did this by using the           command: python3 -m http.server 8080 --bind 127.0.0.1
   - This created a simple test website that was available only on my local computer.p
   - The --bind 127.0.0.1 option limited the server to localhost. This helped keep the exercise       inside my authorized lab environment

  Phase 3; Scan the New Port
    - After starting the Python server, I scanned port 8080 by using command: nmap -sT -sV -p         8080 127.0.0.1

  Results:
      This time, Nmap found port 8080 open.  It also recognized that an HTTP service was running and identified the Python version information 

What I Learned: 
  The first scan showed that ports 22,80, and 443 were closed. After I started the Python web server, port 8080 became open .  An open port usually means that a program or service is listening for network connections.  An open port is not automatically a security problem.  It is important to understand what service is using the port and whether that service should be available.
    In this lab, the web server was intentionally started for testing and was limited to my own  computer

Basic Security Recommendations:
    Based on what I learned, some basic recommendations are 
      - Turn off services that are not needed
      - Only allow access to services that need to be available. 
      - Keep Software updated
      - Check open ports regularly
      -  Only Scan Systems that I own or have permission to test. 


Skills Practiced:
      - Using the Kali Linux terminal
      - Navigating folders and working with files 
      - Running basic Nmap scans
      - Checking whether ports are open or closed
      - Identifying a basic network service
      - Starting a temporary Python web server
      - Saving scan results
      - Writing simple security notes
      - Troubleshooting commands
Evidence Files
  - first-scan.txt -- Results from the first scan
  - open-port-scan.txt -- Results showing the open port and Python web service

Conclusion:
      This was a beginner-level introduction to network scanning with Nmap.  I learned how to check TCP ports, compare closed and open ports, start a simple test service, and used Nmap to identify that service.  
      This project helped me understand how cybersecurity analyst begin gathering information about network services in a controlled and authorized environment.  

# Cybersecurity Incident Report

## Section 1: Identify the type of attack that may have caused this network interruption

One potential explanation for the website's connection timeout error message is because of a DoS SYN flood attack. 
The log shows that the attacker takes advantage of the TCP protocol’s three way handshake to overload the web server. 

Deeply examining the log shows that the attack really comes from the 203.0.113.0 source IP address. This source IP address 
sends a lot of SYN requests to the web server and overloads the server with these requests. This creates a timeout error message 
and hinders employee access to the server. 

## Section 2: Explain how the attack is causing the website to malfunction
Three way hand-shake for TCP connection: 
1. First website visitor’s device sends a SYN packet to the web server to request a connection.
2. The web server sends a SYN/ACK package back to the website visitor’s device to acknowledge and accept the connection.
3.  The final handshake process that connects both of the devices is when the website visitor sends back the ACK package.
his finalizes the process of forming the three-way handshake using TCP protocol.

When a malicious actor sends a large number of SYN packets all at once, it uses up all of the resources of the web server. 
Since there are a lot of packets sent, all the servers are busy and overloaded with requests, which hinders TCP connection 
with legitimate users. The logs clearly show that the server is unable to respond(because of so many requests). New connections 
cannot be made because all the servers are overloaded. We can see that the 203.0.113.0 IP address sends more than 75 SYN requests 
in the spam of 30 seconds which overloads the server.



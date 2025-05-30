# Cybersecurity Incident Report:
## Network Traffic Analysis
### Part 1: Provide a summary of the problem found in the DNS and ICMP 
traffic log.
The UDP protocol reveals that the request to retrieve the IP address for “yummyrecipesforme.com” did not go through. 
After the request is sent we receive a ICMP (Internet control message protocol) message which is a protocol for communicating
network errors. If we receive a message with this protocol, then we should be aware that something went wrong with our request.
We can identify where things went wrong by closely examining the response we get. Based on the result of the tcpdump, we get an
ICMP error message of udp port 53 unreachable of length 150.” The port noted in the error message is port 53 and this port is used
for Domain name system(DNS) communication. Examining the error message, we also see that the issue is with the DNS. It says that 
“ port 53 unreachable”, which is mostly likely due to the fact that there is a problem in the DNS server. The problem associated with
the DNS server has caused none of the user requests to go through and get the webpage. 

### Part 2: Explain your analysis of the data and provide at least one cause of the incident.
The incident occurred at 1:24 p.m. The  organization  provides IT services and one of their clients is the yummyrecipesforme website. 
The organization’s IT team became aware of the incident after a number of customers notified the company that they were unable to access
the “http://www.yummyrecipesforme.com” website. Customers reported that they saw the error “destination port unreachable” after waiting 
for the page to load. The IT department is investigating the incident by using network analyzers, such as tcpdump, to perform packet sniffing.
Based on the investigation, we found out that the DNS server is unreachable. The DNS server might be unreachable due to various reasons, such 
as a DoS attack, a firewall/security group that blocks the traffic, error in the server, or some other malicious software. 

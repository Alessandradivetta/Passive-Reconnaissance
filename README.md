# Passive-Reconnaissance
Learn about the essential tools for passive reconnaissance, such as whois, nslookup, and dig.

Reconnaissance (recon) can be defined as a preliminary survey to gather information about a target. We divide reconnaissance into:

Passive Reconnaissance

Active Reconnaissance

In passive reconnaissance, you rely on publicly available knowledge. It is the knowledge that you can access from publicly available resources without directly engaging with the target and it includes:
Looking up DNS records of a domain from a public DNS server.
Checking job ads related to the target website.
Reading news articles about the target company.

Active reconnaissance, on the other hand, requires direct engagement with the target.
Examples of active reconnaissance activities include:
Connecting to one of the company servers such as HTTP, FTP, and SMTP.
Calling the company in an attempt to get information (social engineering).
Entering company premises pretending to be a repairman.

We will focus on three essential tools related to passive reconnaissance:

whois to query WHOIS servers

nslookup to query DNS servers

dig to query DNS servers

# WHOIS command
The whois command is used to obtain information about a domain, IP address, or autonomous. Here is how it works:

Basic usage:
You can run the command in the terminal like this:
```
whois example.com
```
In this way, you will obtain the domain name, registrant contact administrative contact technical contact name server creation date, expiration date.
# nslookup command
"Name Server Look Up" is a tool used to query DNS servers and obtain information about domains and IP addresses. Here is an overview of how it works:
```
nslookup example.com
```
The output provides information such as:
IP address associated with the domain; DNS server used for the query;  additional information about the DNS records, such as A, MX, TXT records, etc.

Also, nslookup is useful for diagnosing DNS resolution problems and obtaining information about a domain's DNS records.
You can specify a DNS server other than the default one, for example:
```
nslookup example.com 8.8.8.8
```
Let’s say you want to learn about the email servers and configurations for a particular domain. You can issue:
```
nslookup -type=MX example.com
```
For more advanced DNS queries and additional functionality, you can use dig, the acronym for “Domain Information Groper,” if you are curious.

Let’s use dig to look up the MX records and compare them to nslookup. We can use dig example.com, but to specify the record type, we would use: 
```
dig example.com MX
```
Optionally, we can select the server we want to query using dig @SERVER DOMAIN_NAME TYPE.
A quick comparison between the output of nslookup and dig shows that dig returned more information, such as the TTL (Time To Live) by default.

_______________________________________________________________________________________________________________________________________________


# Active - reconnaissance
Now we will focus on the active - reconnisance, which requires you to make some kind of contact with your target. 
This contact can be a phone call or a visit to the target company under some pretence to gather more information, usually as part of social engineering. Alternatively, it can be a direct connection to the target system, whether visiting their website or checking if their firewall has an SSH port open. 
We'll discuss using simple tools such as ping, traceroute, telnet, and nc to gather information about the network, system, and services.

# Telnet command
After the active reconnaissance phase, we need to know what programs are running on the victim's device and know what softwares are present and their versions. This phase is called the “banner grabbing” phase, which we will activate through the telnet, nestat, and nmap command
```
telnet example.com
```

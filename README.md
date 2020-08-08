## eJPT Tools
 My list of tools for the eJPT exam.

# List of Well-known Ports

* SSH (22)
* SMTP (25)
* POP3 (110)
* IMAP (143)
* HTTP/S (80, 443)
* NETBIOS WINS/SMB (137, 139/445)
* SFTP (115)
* Telnet (23)
* FTP Communication/DataTransfer (21, 20)
* RDP (3389)
* MySQL (3306)
* MS SQL Server (1433)


# Common Tools/Commands

* netstat -tunp
* ARP checks
    - arp -a
    - ip neighbour
* nsloookup
* whois
* sublist3r -d [domain]


# Network Scanning Tools

1. fping -a -g [IPRANGE] 2>/dev/null > output.txt

2. Nmap 
    * -sn (ping scan)
    * -sT (TCP connect scan)
    * -sS (SYN only scan, Stealthy)
    * -iL [fileList]
    * -Pn (Treat all hosts as online)
    * -O (OS Detection Enabled)
    * -sV (Version detection scan)

# Vulnerability Scanning Tools

3. Nessus

4. OpenVAS

# Web Application Scanning Tools

5. BurpSuite
    * java -jar [BurpsuiteOlderVersions.jar] 

6. ZAP 
    * Use for Spidering Tool



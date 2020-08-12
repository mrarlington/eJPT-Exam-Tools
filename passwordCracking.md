# Password Cracking Tools

## John The Ripper

Used to crack 

   * /etc/passwd
   * /etc/shadow

First unshadow files
```
$unshadow passwd shadow > outpuhashes.file
```

```
$john --wordlist=/usr/share/john/password.lst hashes.file
```

## Rainbow Tables / Ophcrack


## Hashcat

Hashcat Switches

    * -m Hashes Modes/Types
    * -a Attack type
    * -o Output to a file
    * -b Run a benchmark
    * -d Specify the device
    * -O Optimize performance


## Hydra

Hydra module information

```
$hydra -U rdp
$hydra -U http-get
$hydra -U http-form-post
```


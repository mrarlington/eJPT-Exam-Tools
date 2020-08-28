# Metasploit and Meterpreter Tips

Before starting Metasploit
    
```
$service postgresql start
```
    

## Metasploit

Commands
* Search -h

Do an arp scan 
* arp_sweep
* portscan


## Meterpreter

Commands
* Help or "?"
* Background
* Sessions -i 1 (Session ID)
* Sysinfo
* Getpid (To get current pid)
* Download FILENAME /root/
* Getsystem
* run post/windows/gather/win_privs (Check user priviledges)
* Bypassuac
* ps -U SYSTEM (Gets Processes run by the SYSTEM)

Try to migrate to a diffferent process
   
    * migrate NEWPID  (Migrates to the new PID)




# linux-privilege-escalation
Will provide some useful commands for Linux Privilege Escalation.

# 1 Kernel exploitation/exploits
command: ```searchsploit linux (version) (dist) priv esc``` 

example: ```searchsploit linux kernel 5.9.0 debian priv esc```

other useful tools: 

https://github.com/jondonas/linux-exploit-suggester-2

https://github.com/linted/linuxprivchecker

https://github.com/AlessandroZ/BeRoot

https://pentestmonkey.net/tools/audit/unix-privesc-check

# 2 Service Exploits
The following command shows all services running as root:
```
  ps aux | grep "^root"
```

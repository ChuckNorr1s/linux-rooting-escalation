# Linux Privilege Escalation Cheat Sheet

This cheat sheet provides useful commands and tools for Linux Privilege Escalation.

## Kernel Exploitation/Exploits

To search for available kernel exploits for a specific version and distribution, use the following command:

```searchsploit linux <version> <distribution> priv esc```


For example:

```searchsploit linux kernel 5.9.0 debian priv esc```


You can also use the following tools:

- [linux-exploit-suggester-2](https://github.com/jondonas/linux-exploit-suggester-2)
- [linuxprivchecker](https://github.com/linted/linuxprivchecker)
- [BeRoot](https://github.com/AlessandroZ/BeRoot)
- [unix-privesc-check](https://pentestmonkey.net/tools/audit/unix-privesc-check)

## Service Exploits

To identify services running as root, use the following command:

```ps aux | grep "^root"```

Note: This command only shows services running as root. It may not provide a complete list of all services running on the system.

## Enumerating Program Versions

- To check the version of a particular program installed on the system, use the following command:

```<program> --version```

For example:

```gcc --version```

- To check the version of all installed packages, use the following command:

```dpkg -l```

This command lists all the packages installed on the system along with their version numbers.

- To check the version of all running services on the system, use the following command:

```netstat -tulpn```

This command lists all the running services on the system along with their port numbers. You can then use the port number to identify the service and check its version.

- To check the version of a particular library installed on the system, use the following command:

```ldconfig -p | grep <library>```

For example:

```ldconfig -p | grep libssl```

This command lists all the libraries installed on the system that match the given search pattern along with their version numbers.

- To check the version of the Linux kernel installed on the system, use the following command:

```uname -r```

This command displays the version of the Linux kernel currently running on the system.

- To check the version of the distribution, use the following command:

```lsb_release -a```


This command displays information about the Linux distribution installed on the system, including its version.

## Port Forwarding

If a root process is bound to a local port, you can forward traffic to that port to your local machine using the following command:

```ssh -L <local_port>:localhost:<remote_port> user@hostname```

Replace `<local_port>` with the local port number you want to forward traffic to, and `<remote_port>` with the remote port number the root process is bound to. Replace `user` and `hostname` with the username and hostname of the remote machine. You will need to enter the remote user's password when prompted.

Once the port is forwarded, you can access the service running on the remote machine at `localhost:<local_port>` on your local machine.


## References

- [Linux Exploit Suggester 2](https://github.com/jondonas/linux-exploit-suggester-2)
- [Linux Privilege Escalation Cheatsheet](https://book.hacktricks.xyz/linux-unix/linux-privilege-escalation-cheat-sheet)
- [BeRoot](https://github.com/AlessandroZ/BeRoot) 
- [Unix Privilege Escalation Check Script](https://pentestmonkey.net/tools/audit/unix-privesc-check)

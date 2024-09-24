# tcpping v2.x

A (quick and dirty) tool to ping TCP / UDP service ports  

**Warning: With version 2.4, some defaults have changed:**
   - Default timeout is now 1 second instead of 3
   - Interval between pings is now automatically calculated to fit timeout

These changes have been made to make Smokeping integration easier.

## fork of elder tcpping v1.8 script running with newer traceroute binary

This script is a fork of Richard Van den Berg's tcpping script, original version found [here](https://github.com/deajan/tcpping/tree/original-1.8), supporting newer traceroute binaries.
Usage is the same and should work out of the box for smokeping.

It comes with various improvements like language agonstic functionality, better error detection, debug, and removed tcptraceroute dependancy, sub second pings and statistics.

So far, tests have been done with:
- CentOS 7: v2.0-2.3 tested (with traceroute 2.0.22 and bash 4.2.46(2)-release)
- CentOS 8: v2.3 tested (with traceroute 2.1.0 and bash 4.4.19(1)-release)
- AlmaLinux 9: v2.5 tested (with traceroute 2.1.0 and bash 5.1.8(1)-release)
- FreeBSD 11.2: v2.0-2.3 tested (with traceroute 1.4a12 and tcsh 6.20.00)
- Debian 12: v2.5 tested (with traceroute 2.1.2 and dash 0.5.12-2)
Also, smokeping 2.7.2 and 2.7.3 have been tested.

The script works on bash, dash and zsh interpreters.

## Installation

```
sudo curl -o /usr/local/bin/tcpping -L https://raw.githubusercontent.com/deajan/tcpping/master/tcpping ; sudo chmod 755 /usr/local/bin/tcpping
```

## Usage

Example command smokeping would use

`tcpping -C -x 5 myhost 80`

Example command for sub second tcp ping analysis on Linux

`tcpping -x 10 -w .1 -o myhost 443`

Keep in mind that the tcp / udp probe checks for a SYN flag, which does not mean that a service is listening on the target machine port.

## Root privileges

By default, traceroute needs root privileges.
You may launch script with sudo or with '-Z' in order to ask for root privileges during execution.
By doing so, you may edit your sudoers file by allowing user 'bob' to run traceroute as root without password
```
bob ALL=(ALL) NOPASSWD: /usr/bin/traceroute
```

## Licence and improvements

Altough there are probably better tools out there (hping, nmap, etc), this is still a quick and handy tool used by smokeping, so every improvement / fork / pull request is more than welcome.

Originally, Richard linked to the GPLv2 licence.
Having talked with him, he did allow to update to GPLv3, so this script is GPLv3.

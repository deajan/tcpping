# tcpping

## fork of elder tcpping v1.8 script running with newer traceroute binary

This script is a fork of Richard Van de Berg's tcpping script, supporiting newer traceroute binaries.
Usage is the same and should work out of the box for smokeping.

It comes with various improvements like language agonstic functionality, better error detection, debug, and removed tcptraceroute dependancy.

This is still a basic work and has only been tested on CentOS 7, FreeBSD 11 and smokeping 2.7.2 so far.
On CentOS 7, traceroute 2.0.22  has been tested.
On FreeBSD, traceroute 1.4a12 has been tested.

## Installation

`sudo wget -O /usr/bin/tcpping https://raw.githubusercontent.com/deajan/tcpping/master/tcpping ; chmod 755 /usr/bin/tcpping`

## Usage

Example command smokeping would use

`tcpping -C -x 5 myhost 80`

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

# tcpping

## fork of elder tcpping v1.8 script running with newer traceroute binary

This script is a fork of Richard Van de Berg's tcpping script, supporiting newer traceroute binaries.
Usage is the same and should work out of the box for smokeping.

It comes with various improvements like language agonstic functionality, better error detection, debug, and removed tcptraceroute dependancy.

This is still a basic work and has only been tested on CentOS 7, FreeBSD 11 and smokeping 2.7.2 so far.

## Installation

`sudo wget -O /usr/bin/tcpping https://raw.githubusercontent.com/deajan/tcpping/master/tcpping ; chmod 755 /usr/bin/tcpping`

## Usage

Example command smokeping would use

`tcpping -C -x 5 myhost 80`


## Licence and improvements

Altough there are probably better tools out there (hping, nmap, etc), this is still a quick and handy tool used by smokeping, so every improvement / fork / pull request is more than welcome.
Richard linked to the GPL licence which was GPLv2 at the time of the script being written, but now the link points to GPLv3 so I guess we're good with the current GPL version.

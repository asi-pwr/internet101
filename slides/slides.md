% Internet 101
% Michał Zając

# History

## Creation

tl;dr The internet is a side effect of ARPANET project

::: notes
Advanced Research Projects Agency NETwork tried to build a network that could survive a nuclear attack
:::

## The great divide

Military got fed up with people browsing their stuff.

# Physical media

## Bandwidth

How many bits per second can the media handle?

## Latency

How long does it take for one bit to reach the other end?

## Electricity

8P8C connector over Cat 3 - Cat 8 cable

::: notes
Most popular is Category 7 which allows up to 10 Gbit over 100m of cable
:::

## Light

Optic fibres

::: notes
Depending on the bounce angle we can actually send multiple bits simulatneously
:::

## Radio waves

WiFi obviously

# IP

## v4

An IPv4 address is made of 4 octets. It's kind like an address

## IPv4 address example

```
8.8.8.8

00001000 00001000 00001000 00001000
```

## IPv4 packet example

![IPv4 packet segment](images/ipv4packet.png){.stretch}\ 

Source: Wikipedia

## v6

An IPv6 address is made of 8 16bit blocks

## IPv6 example

```
2001:0DB8:0000:0000:0000:0000:1428:57AB
2001:db8::1428:57ab
```

# TCP & UDP

## TCP

A client-server protocol

::: notes
Server awaits connection at a certain point. Once a client initiates the connection the transmission starts.
In contrast to UDP, TCP makes sure that ALL packets will arrive in order and with no duplicates.
For every packet sent the target device sends an acknowledgement. In case of missing packets a retransmission request can be issued
:::

## TCP packet structure

![TCP packet structure](images/tcppacket.png){.stretch}\ 

Source: Wikipedia

## UDP

A connectionless protocol

::: notes
Just send the packet along with a checksum. Gives no guarantees the packets will reach the target
:::

## UDP packet structure

![UDP packet structure](images/udppacket.png){.stretch}\ 

Source: Wikipedia

# DNS

## Problem

Who the hell remembers IP addresses?

## Solution

applover.pl instead 195.201.74.26

## Problem

How to translate from applover.pl to 195.201.74.26?

## Solution

DNS

## Working example

| Source | Destination | Message |
|:-------|:------------|:--------|
| Browser | ISP DNS | Hey, got IP address of pl.wikipedia.org? |
| ISP DNS | Root DNS | Oy mate, got IP address of pl.wikipedia.org? |
| Root DNS | ISP DNS | Nope, but ask 204.74.112.1 about org domain |
| ISP DNS | org DNS | Ay fam, got IP for pl.wikipedia.org? |
| org DNS | ISP DNS | Nope, ask 216.21.226.87 about wikipedia.org domain |
| ISP DNS | wikipedia.org DNS | Hi, can I have IP address for pl.wikipedia.org? |
| wikipedia.org DNS | ISP DNS | pl.wikipedia.org is 207.142.131.245 |
| ISP DNS | Browser | pl.wikipedia.org is 207.142.131.245 |
| Browser | pl.wikipedia.org | GET / HTTP/1.1 |

::: notes
There are 13 root DNS servers because an UDP packet can fit only that much information
:::

# Wrapping up

# Questions?

# Further reading

##

#. [ARPANET](https://en.wikipedia.org/wiki/ARPANET)
#. [Internet Protocol](https://en.wikipedia.org/wiki/Internet_Protocol)
#. [Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)
#. [User Datagram Protocol](https://en.wikipedia.org/wiki/User_Datagram_Protocol)
#. [Domain Name System](https://en.wikipedia.org/wiki/Domain_Name_System)

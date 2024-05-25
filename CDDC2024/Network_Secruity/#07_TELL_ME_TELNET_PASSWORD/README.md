# Challenge Name: <#07 TELL ME TELNET PASSWORD>

- Category: Network Security
- Points: <100>
- Solves: <201>

## Challenge Description

I captured a network packet contaning telnet, can you find the password?

Wrap the flag in format CDDC2024{}

## File Content

tell_me_telnet.pcap

## Solution

We know that the packet we have to inspect is a telnet protocol. Inpsecting the TCP stream for telnet protocols, we chance upon this packet:

![Screenshot of the challenge](/Images/CDDC2024_Training/networksec_07.png)

We can see that the password was invalid due to part of the password being keyed before the server requested for the password. Hence, piecing together p and asswordiskisapasswordddddddddddd, we get the flag

## Flag

CDDC2024{passwordiskisapasswordddddddddddd}

## Notes

Reference: https://medium.com/@prosperudofot/telnet-packet-capture-analysis-with-wireshark-eb6243dbaf91 

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

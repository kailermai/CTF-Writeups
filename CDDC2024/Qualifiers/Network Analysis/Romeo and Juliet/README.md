# Challenge Name: <#Romeo and Juliet>

- Category: Network Analysis
- Points: <100>
- Solves: <325>

## Challenge Description

Romeo and Juliet couldn't exchange letters because of the strong opposition between their families.
To continue the romance, Romeo and Juliet now use PCs to exchange letters.
One day, Juliet accidentally deleted Romeo's latest letter from her PC, therefore could not read important information in the letter.
Romeo had already deleted the letter, too.

Analyse and retrieve the message from the deleted letter.

Flag format : CDDC24{   }

## File Content

Romeo.pcap

## Solution

Following the TCP stream, we can see that the exchanges were using HTTP protocol and GET requests. We can then filter to HTTP protocols:

![Screenshot of the challenge](/Images/CDDC2024_Qualifiers/Qualifier_NetworkAnalysis_Romeo.png)

Trying CDDC24{Juliet_wedding_ring} does not get us the flag, so we look into the jpg file that was sent, using file and exporting the jpg.

![Screenshot of the challenge](/Images/CDDC2024_Qualifiers/Qualifier_NetworkAnalysis_Romeo2.jpg)

## Flag

CDDC24{M4rry_M3_Ju1iet}

## Notes

Reference: https://medium.com/@prosperudofot/telnet-packet-capture-analysis-with-wireshark-eb6243dbaf91 

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

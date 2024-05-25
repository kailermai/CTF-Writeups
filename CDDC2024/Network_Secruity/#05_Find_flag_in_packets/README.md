# Challenge Name: <#02 udppp>

- Category: Network Security
- Points: <200>
- Solves: <263>

## Challenge Description

I am someone who only uses the HTTP protocol. Perhaps because of this, I accidentally accessed a website with sensitive information entered. Find out what information has been leaked.

## File Content

Find flag in packets.pcapng

## Solution

We know that the protocol used was HTTP, hence we cann filter HTTP protocols in wireshark.

![Screenshot of the challenge](/Images/CDDC2024_Training/networksec_05.png)

Inpsecting the info column, we can see the user has sent some get requests to obtain the flags. We can access them by going to file and exporting http.

![Screenshot of the challenge](/Images/CDDC2024_Training/networksec_05p2.png)

We can then see that there are 3 flags for us to try

## Flag

CDDC2024{HTTP_IS_VERY_GOOD}

## Notes

NIL

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

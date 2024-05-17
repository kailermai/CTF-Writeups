# Challenge Name: <#03 Where Is The FLAG>

- Category: Linux
- Points: <100>
- Solves: <180>

## Challenge Description

Where is the secret FLAG?

nc 3.1.147.170 10002

## Hint

Security is important in the /etc directory in Linux because it contains system-wide configuration files! Take a look in that directory!

## Solution

Using nc, I communicated with 3.1.147.170 on port 10002

`nc 3.1.147.170 10002`

With the hint, I changed the directory into /etc and used the cat command to read the passwd file, obtaining the flag.

```
cd /etc
cat passwd
```

## Flag

CDDC2024{vERRRRRy1mportAnTFIlE}

## Notes

The cat command in Linux is more than just a simple tool; it’s a versatile companion for various file-related operations, allowing users to view, concatenate, create, copy, merge, and manipulate file contents

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

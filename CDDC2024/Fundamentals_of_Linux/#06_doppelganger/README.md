# Challenge Name: <#06_doppelganger>

- Category: Linux
- Points: <100>
- Solves: <156>

## Challenge Description

Lots of flag, but can you find the real one?

nc 3.1.147.170 10005

## Solution

Use ls and we see that there is only a flag.txt file. However, using cat to read it will give us many flags with only 1 unique flag.

To find a flag that is unique, we can use this linux command with a pipe:

`sort flag.txt | uniq -u`

## Flag

CDDC2024{4r3_yOu_7He_cH00sEn_0n3_Ne0_r2D23}

## Notes

https://www.geeksforgeeks.org/piping-in-unix-or-linux/
https://www.geeksforgeeks.org/uniq-command-in-linux-with-examples/

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

# Challenge Name: <#06 traverse>

- Category: Web Security
- Points: <100>
- Solves: <95>

## Challenge Description

Here is the folder structure, can you find the flag?

http://47.128.156.184:10004/ 

uploads/uploaded.txt
uploads/random.txt
hello.txt
not-a-flag.txt
index.php

Directory enumeration is not required to solve this challenge.

## Hint

Its actually an inclusion rather than traverse..

## Solution

With the hint, we can use ?file= to send a http request to get a file. Using http://47.128.156.184:10004/?file=not-a-flag.txt gets us access denied, but accessing the files in uploads fetches us the files in the folder. Using .. to return back to the original directory, we can now access the files in the original folders. Accessing http://47.128.156.184:10004/?file=uploads/../index.php and inspecting the html code, we get the flag.

## Flag

CDDC2024{w0W_y0U_m4NaG3d_t0_g3t_h3Re}

## Notes

NIL

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

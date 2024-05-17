# Challenge Name: <#05 Source>

- Category: Web Security
- Points: <100>
- Solves: <182>

## Challenge Description

I just made a website

http://47.128.156.184:10003/ 

## Solution

![Screenshot of the challenge](/Images/websecurity_05source.png)

Inspecting the webpage, we get the first part of the flag in the html source code.
`CDDC2024{1_L0v3_w3B (1/4)`

With the stylesheet linked, we can access it by http://47.128.156.184:10003/static/index.css, obtaining the second part of the flag.
`s17E_cH4LLeN9 (2/4)`

With the hint in the html code:

```
Note to self:
Don't forget to remove show_flag() function.    
```

We can head to console and type show_flag() to get the third part.
`e5_4nD_1_L0 (3/4)`

For the fourth part of the flag, I inspected the cookies value in applications header.
`ve_kiM_m1Nj00} (4/4)`


## Flag

CDDC2024{1_L0v3_w3Bs17E_cH4LLeN9e5_4nD_1_L0ve_kiM_m1Nj00}

## Notes

NIL

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

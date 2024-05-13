# Challenge Name: <#03 find me>

- Category: Linux
- Points: <200>
- Solves: <180>

### Challenge Description:

There is a Flag file! But I can't read it.
Who can read that file?

nc 3.1.147.170 10003

### Solution

Using nc, I communicated with 3.1.147.170 on port 10003

`nc 3.1.147.170 10003`

Use ls and we get the list of files:

- account.list
- flag1.txt
- flag2.txt

The account list with different users and passwords have also been provided, but we can use cat to access the account.list file as well.

`cat account.list`

However, trying to read the flag files will lead to permission denied error. Hence, with the hint in the question, I switched users using the su command, finding the user that can access the flag files, obtaining the flag.

`su ashe`
`Password: J0SoDPhHEtt0ccp`
`cat flag1.txt`
`Congratulation! flag is CDDC2024{ThaaAnkUF0rf1nd`
`su poppy`
`Password: 7PsISFc0YYTCqSD`
`cat flag2.txt`
`myaAaACC0unT}`

### Flag

CDDC2024{ThaaAnkUF0rf1ndmyaAaACC0unT}

### Notes

The su (short for substitute or switch user) utility allows you to run commands with another user’s privileges, by default the root user.

Using su is the simplest way to switch to the administrative account in the current login session. This is especially handy when the root user is not allowed to log in to the system through ssh or using the GUI display manager.

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

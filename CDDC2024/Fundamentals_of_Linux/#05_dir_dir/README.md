# Challenge Name: <#05_dir_dir>

- Category: Linux
- Points: <100>
- Solves: <204>

### Challenge Description:

Can you find the flag across these folders?

nc 3.1.147.170 10004

### Solution

Use ls and we get the list of files:

- 0
- 1
- 2
- 3
- 4
- 5
- 6
- 7
- 8
- fake_flag.txt

There seems to be more sub-folders within these folders. It seems that we can brute force each directory to find flag.txt, but we can use the find command to search for flag.txt

`find . -name "flag.txt"`
./8/7/4/1/0/6/flag.txt

With this, we know that the flag is in the directory ./8/7/4/1/0/6/flag.txt, and we can access it with cat to get the flag.

### Flag

CDDC2024{f1Nd3rS_KE3PErs}

### Notes

https://www.geeksforgeeks.org/find-command-in-linux-with-examples/

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

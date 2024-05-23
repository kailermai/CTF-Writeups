# Challenge Name: <03 random>

- Category: Cryptography
- Points: <100>
- Solves: <171>

## Challenge Description

oh no, it is random! how to break the cipher?

## File Content

random.zip

- enc (text file)

```
XISF8462{aS_r2_Qs7_o4kVas_c4Ih4d_4jV9o_3SI}
```

- chall.py

```
import random

def encrypt_flag(flag):
    flag_enc = ""
    random.seed("​".join(["leet", "1337"]))
    for c in flag:
        if c.islower():
            shift = random.randint(1, 26)
            flag_enc += chr((ord(c) - ord('a') + shift) % 26 + ord('a'))
        elif c.isupper():
            shift = random.randint(1, 26)
            flag_enc += chr((ord(c) - ord('A') + shift) % 26 + ord('A'))
        elif c.isdigit():
            shift = random.randint(1, 10)
            flag_enc += chr((ord(c) - ord('0') + shift) % 10 + ord('0'))
        else:
            flag_enc += c
    return flag_enc

flag = open("flag", "r").read().strip()
encrypted_flag = encrypt_flag(flag)
print("Encrypted flag:", encrypted_flag)
```

## Solution

Initially, I assumed that the encryption was random due to the use of the random function. However, using ChatGPT to explain the code to me, I found out that the seed of the random function matters in generating the "random" number. Using the same seed, the number generated would always be the same. Hence, we can reverse engineer the code, using the same seed to decrypt it.

```
import random

def decrypt_flag(flag):
    flag_enc = ""
    random.seed("​".join(["leet", "1337"]))
    for c in flag:
        if c.islower():
            shift = random.randint(1, 26)
            flag_enc += chr((ord(c) - ord('a') - shift) % 26 + ord('a'))
        elif c.isupper():
            shift = random.randint(1, 26)
            flag_enc += chr((ord(c) - ord('A') - shift) % 26 + ord('A'))
        elif c.isdigit():
            shift = random.randint(1, 10)
            flag_enc += chr((ord(c) - ord('0') - shift) % 10 + ord('0'))
        else:
            flag_enc += c
    return flag_enc

flag = open("enc", "r").read().strip()
decrypted_flag = decrypt_flag(flag)
print("Decrypted flag:", decrypted_flag)
```

Changing the `+ shift` into a `- shift` would reverse the encryption process, hence by running the python script, we obtain the flag.

## Flag

CDDC2024{iT_i5_No7_r3aLly_r4Nd0m_4fT3r_4LL}

## Notes

NIL

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

# Challenge Name: <#04 vigenere>

- Category: Cryptography
- Points: <200>
- Solves: <123>

## Challenge Description

Ciphertext: KOBK2024{q_J0Gc_e0_pY7_n1kX4}

Can you guess the key?

## File content

- vigenere_public.py

```
import random

def generate_vigenere_challenge(plaintext, key_length):
    key = ''.join(random.choice('ABCDEFGHIJKLMNOPQRSTUVWXYZ') for _ in range(key_length))
    ciphertext = ''
    for i, char in enumerate(plaintext):
        key_char = key[i % key_length]
        if char.isalpha():
            shift = ord(key_char.upper()) - ord('A')
            if char.islower():
                ciphertext += chr((ord(char) - ord('a') + shift) % 26 + ord('a'))
            else:
                ciphertext += chr((ord(char) - ord('A') + shift) % 26 + ord('A'))
        else:
            ciphertext += char
    return plaintext, key, ciphertext

def main():
    plaintext = "CDDC2024{this_is_a_flag}"
    key_length = 3
    plaintext, key, ciphertext = generate_vigenere_challenge(plaintext, key_length)

    print("Vigenère Challenge:")
    print("Plaintext:", plaintext)
    print("Key:", key)
    print("Ciphertext:", ciphertext)

if __name__ == "__main__":
    main()
```

## Solution

With the source code containing the code that generated the encrypted flag, I adjusted the python code:

```
def main():
    plaintext = "KOBK2024{q_J0Gc_e0_pY7_n1kX4}"
    key_length = 3
    plaintext, key, ciphertext = generate_vigenere_challenge(plaintext, key_length)

    print("Vigenère Challenge:")
    print("Plaintext:", plaintext)
    print("Key:", key)
    print("Ciphertext:", ciphertext)

    while "CDDC" not in ciphertext:
        plaintext, key, ciphertext = generate_vigenere_challenge(plaintext, key_length)

        print("Vigenère Challenge:")
        print("Plaintext:", plaintext)
        print("Key:", key)
        print("Ciphertext:", ciphertext)
```

By adjusting the plaintext to the given encrypted flag, KOBK2024{q_J0Gc_e0_pY7_n1kX4}, and adding a while loop, I was able to loop over the algorithm to generate a ciphertext with different keys until I obtained a ciphertext with the keyphrase "CDDC" in it, obtaining the flag:

```
Plaintext: KOBK2024{q_J0Gc_e0_pY7_n1kX4}
Key: SPC
Ciphertext: CDDC2024{i_L0Ve_t0_eA7_p1zZ4}
```

## Flag

CDDC2024{i_L0Ve_t0_eA7_p1zZ4}

## Notes

NIL

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

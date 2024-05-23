# Challenge Name: <04 pycon>

- Category: Cryptography
- Points: <100>
- Solves: <148>

## Challenge Description

Do you like spaghetti? here is spaghetti code for u

## File Content

pycon.zip

- enc (text file)

```
w5LDnMOcw5IwNDA8wqLChsOqwoQ0wrQyw6rCpsOKwr7DqsKMNsKCw57DqsK8NMOqwrAyw5bCnMOqwpI0w5wywq4=
```

- chall.py

```
import base64;exec(base64.b64decode("Y3VzdG9tX2VuY3J5cHQgPSBsYW1iZGEgbTogYmFzZTY0LmI2NGVuY29kZSgnJy5qb2luKFtjaHIoKG9yZChjKSBeIDQyKSA8PCAxKSBmb3IgYyBpbiBtXSkuZW5jb2RlKCd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk="))
a = "fake_flag"
encrypted_message = custom_encrypt(a)
print(encrypted_message)

# ENC: w5LDnMOcw5IwNDA8wqLChsOqwoQ0wrQyw6rCpsOKwr7DqsKMNsKCw57DqsK8NMOqwrAyw5bCnMOqwpI0w5wywq4=
```

## Solution

We can decode the text provided using base64 decoding, inferred from base.64.b64decode.

```
custom_encrypt = lambda m: base64.b64encode(''.join([chr((ord(c) ^ 42) << 1) for c in m]).encode('utf-8')).decode('utf-8')
```

With the structure of the encoder deciphered, we can reverse engineer the cipher:

```
import base64

ciphertext = "w5LDnMOcw5IwNDA8wqLChsOqwoQ0wrQyw6rCpsOKwr7DqsKMNsKCw57DqsK8NMOqwrAyw5bCnMOqwpI0w5wywq4="

decodedbytes = base64.b64decode(ciphertext)

decodedstring = decodedbytes.decode('utf-8')

res = ""
for c in decodedstring:
    decodedchar = chr((ord(c) >> 1) ^ 42)
    res += decodedchar

print(res)
```

Printing res gives us the flag.

## Flag

CDDC2024{i_h0p3_yOu_l1kE_t0_r3Ad_c0D3}

## Notes

NIL

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

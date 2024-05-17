# Challenge Name: <#02 YummyCookie>

- Category: Web Security
- Points: <100>
- Solves: <157>

## Challenge Description

I made yummy cookies~

http://47.128.156.184:10000/

## File content

- static
- templates
- app.py
- dockerfile

### Contents of app.py

```
from flask import Flask, request, make_response, redirect, url_for, render_template

app = Flask(__name__)

FLAG = "CDDC{------secret------}"

USERS = {
    "guest": "guest",
    "admin": "------secret------"
}

COOKIES = {
    "guest": "guest",
    "admin": "admin"
}

@app.route('/')
def main():
    cookie = request.cookies.get('cookie', '')
    return render_template('index.html', cookie=cookie)

@app.route('/login', methods=['POST'])
def login():
    user_id = request.form['id']
    password = request.form['password']
    if user_id in USERS and USERS[user_id] == password:
        resp = make_response(redirect(url_for('main')))
        resp.set_cookie('cookie', COOKIES[user_id])
        return resp
    else:
        return 'Login Failed!'

@app.route('/secret')
def secret():
    if request.cookies.get('cookie') == 'admin':
        return FLAG
    else:
        return 'Access Denied!'

if __name__ == '__main__':
    app.run(host="0.0.0.0", port=3000)
```

## Hint

How to access '/secret' page...?

## Solution

With hint and app.py provided, we can see that there are two important pages we can access, /login and /secret. Accessing secrets gets us to an access denied page. From the contents of app.py:

```
@app.route('/secret')
def secret():
    if request.cookies.get('cookie') == 'admin':
        return FLAG
    else:
        return 'Access Denied!'
```

We can see that to access the secret page and get it to return the flag, we need our cookies to be set to admin, else we would see the access denied page. Hence, inspecting the webpage and moving to the application tab, we can get to cookies under the storage header. From there, we can change the value of 'cookie' to admin. Retrying to access the secret page using 47.128.156.184:10000/secret, we get the flag.

## Flag

CDDC2024{hOW2USECooooooooKIE}

## Notes

NIL

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

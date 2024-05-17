# Challenge Name: <#03 Event>

- Category: Web Security
- Points: <100>
- Solves: <162>

## Challenge Description

Enter you name to join the event

http://47.128.156.184:10001/

## File content

- app.py

### Contents of app.py

```
from flask import Flask, render_template, request

app = Flask(__name__)

FLAG = "----secret----"

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/submit', methods=['POST'])
def submit():
    name = request.form['name']
    if "<img" in name and "alert" in name:
        message = "congratulations.       " + FLAG
        return render_template('success.html', message=message, name=None)
    else:
        message = f"{name},Your submission has been successful."
        return render_template('success.html', message=message, name=name)

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=3001)
```

## Solution

In app.py, we can see that the flag will get returned if the name field we submit contains
`<img` and `alert`.

```
 if "<img" in name and "alert" in name:
        message = "congratulations.       " + FLAG
        return render_template('success.html', message=message, name=None)
```

Hence, as long as we include those strings in the name field, it will redirect us to the page with the flag.


## Flag

CDDC2024{MissUP4uLOBENT0}

## Notes

NIL

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

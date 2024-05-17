# Challenge Name: <#04 Master>

- Category: Web Security
- Points: <100>
- Solves: <143>

## Challenge Description

You can inquire about student information
by entering your name and student number!

http://47.128.156.184:10002/ 

## File content

- templates
    - hello.html
    - result.html
- app.py

### Contents of app.py

```
from flask import Flask, render_template, request
from flask_sqlalchemy import SQLAlchemy
from sqlalchemy import text


app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///./test.db'
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
db = SQLAlchemy(app)

class Student(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(80), unique=True, nullable=False)
    student_id = db.Column(db.String(20), unique=True, nullable=False)
    major = db.Column(db.String(100), nullable=False)
    role = db.Column(db.String(20), nullable=False, default='student')

@app.before_first_request
def create_tables_and_add_test_data():
    db.create_all()
    if Student.query.count() == 0:
        students = [
            Student(name='Alice', student_id='2021001', major='Computer Science', role='student'),
            Student(name='Bob', student_id='2021002', major='Mathematics', role='student'),
            Student(name='Charlie', student_id='2021003', major='Physics', role='student'),
            Student(name='Diana', student_id='2021004', major='Chemistry', role='student'),
            # Student(name={REDACTED}, student_id={REDACTED}, major={REDACTED}, role={REDACTED})
        ]
        db.session.bulk_save_objects(students)
        db.session.commit()

@app.route('/', methods=['GET', 'POST'])
def index():
    flag = None
    major = "Not found, please try again" 
    if request.method == 'POST':
        name = request.form.get('name')
        student_id = request.form.get('student_id')
        query = text(f"SELECT * FROM student WHERE name='{name}' AND student_id='{student_id}'")
        results = db.session.execute(query).fetchall()
        
        if results:
            for result in results:
                if result.role == '{REDACTED}':
                    flag = '----secret----'
                    major = result.major
                    break
                else:
                    major = result.major

        return render_template('result.html', major=major, flag=flag)
    return render_template('hello.html')

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=3002)
```

## Hint

However, due to the fragility of the system,
certain other inputs may cause the system to output flags in error!

## Solution

With the hint and a crucial part of the query code:

```
query = text(f"SELECT * FROM student WHERE name='{name}' AND student_id='{student_id}'")
```

This suggests that it is an SQL injection problem. The website demands 2 input fields, name and student id. However, due to how the query code is structure, we can make use of SQL injection to output the flag.

```
Name:
' or 1=1;--

Class number:
1
```

With these inputs, it puts the query fill to look like this:
`query = text(f"SELECT * FROM student WHERE name='' or 1=1;--' AND student_id='1'")`

This makes the name field '' or 1=1;--, which makes the field True, while the ; ends the code and -- comments the rest of the code out. Hence, the resulting code looks like:

`query = text(f"SELECT * FROM student WHERE name='' or 1=1;`

Since name ends up to be True and class number is not needed, we will get to the flag page.


## Flag

CDDC2024{UUw1llbeeGrE4tH4cK3r}

## Notes

SQL Injection CTF
References: https://ctf101.org/web-exploitation/sql-injection/what-is-sql-injection/

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)

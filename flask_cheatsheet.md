## FLASK App Set-Up

### Terminal:
```bash
mkdir projectName
```
`cd projectName`
#### Virtual Env
- [ ] initialize virtual environment
- [ ] install packages
```bash
pipenv install flask
pipenv shell
```
##### pipenv (other useful commands)
```bash
pipenv --rm
pip list
pipenv sync
pipenv graph
```
#### Initialize Folder Structure
```bash
touch server.py
mkdir flask_app
touch flask_app/__init__.py
cd flask_app
mkdir templates config models static static/imgs controllers
touch templates/index.html static/style.css config/mysqlconnection.py controllers/users_controller.py models/user.py
```

---
### `/server.py`
```python
from flask_app import app
# import controllers 
from flask_app.controllers import users_controller


if __name__ == "__main__":
  app.run(debug=True)
  #optional host='localhost', port=5001
```
---
### `/flask_app/__init__.py`
```python
from flask import Flask
app = Flask(__name__)
app.secret_key = "dsdfhdfgjdfgjsfdhsdfghsdfg"
```
---
### `/flask_app/controllers/users_controller.py`
```python
from flask_app import app
from flask import render_template, redirect, request, session

@app.route('/')
def index():
  return render_template('index.html')
```
---
### `/flask_app/templates/index.html`
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      rel="stylesheet"
      href="{{ url_for('static', filename='css/style.css') }}"
    />
    <title>Index HTML</title>
  </head>
  <body>
    <div id="wrapper">
      <h1 class="subHead">Houston We Have Liftoff!!!!</h1>
      
    </div>
  </body>
</html>

```
---
### Continue with specific project steps/notes befitting your preference
---


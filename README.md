[![Python application test with Github Actions](https://github.com/son-n-pham/scaffold/actions/workflows/pythonapp.yml/badge.svg?branch=main)](https://github.com/son-n-pham/scaffold/actions/workflows/pythonapp.yml)
# scaffold
Python scaffold

![image](https://user-images.githubusercontent.com/79841341/181009154-ad33bd80-3a6b-4248-b675-bf194cc20d0f.png)

ssh in cloud9 of aws:
```
ssh-kegen -t rsa
```
Now git clone ssh

Go to folder cloned from Git Hub, create:
- Makefile

```
install:
	pip install --upgrade pip &&\
		pip install -r requirements.txt
		
install-azure:
	pip install --upgrade pip &&\
		pip install -r requirements-azure.txt
		
format:
	black *.py
	
lint:
	pylinkt --disable=R,C hello.py
	
test:
	python -m pytest -vv --cov=hello test_hello.py
	
all: install lint test
```

- requirements.txt

```
pylint
pytest
click
black
pytest-cov
```

- Python script file hello.py

```python
def add(x, y):
    return x + y

#var=
result = add(1, 2)
print("This is the sum: 1, 2, %s" % result)
```

- Pyunit for testing the script file test_hello.py
```python
from hello import add

def test_add():
  assert add(1,2) == 3
```

- Install virtualenv, then creeate virtualenv, and finally activate the new virtualenv:

```bash
python3 -m pip install virtualenv
virtualenv .scaffold
source .scaffold/bin/activate
```

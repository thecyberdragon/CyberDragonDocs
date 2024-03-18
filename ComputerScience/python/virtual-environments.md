# 🐍 Virtual Environments

Used to control the environment per project

### <mark style="color:yellow;">Installing</mark>

```python
pip install --user pipenv
```

_Installs pipenv on the user level not globally_

Add the filepath in the error to the environment variables

### <mark style="color:yellow;">Using a venv</mark>

Make a folder for the project. cd into the folder in terminal / vscode

```python
pipenv --three
```

_--three means python3_

### <mark style="color:yellow;">Pipfile</mark>

Info on virtual environment & packages that gets created when you create the environment

```python
pipenv install package

# Install version
pipenv install package==0.0.0
```

_installs package and updates virtual environment_

pipfile → package = “\*” means any version

pipfile.lock is created when you install a package. Don’t manually update

### <mark style="color:yellow;">Starting the environment</mark>

```python
pipenv shell
```

Exit from python3 in the shell → exit()

Exit from shell → exit


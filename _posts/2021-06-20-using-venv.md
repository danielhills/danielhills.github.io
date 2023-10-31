---
layout: default
---

# Common venv commands in Python

`2021-06-20`

Useful set of terminal commands for when using virtualenvs in Python. These cover about 99% of my use of venvs.

### Create virtual env
```shell
python3 -m venv venv
```
(2nd argument specifies name of venv)

Note, you can specify python version like so:
```shell
virtualenv venv -p python3.6
```

### Activate the env
```shell
source venv/bin/activate
```

### Install packages on the venv from requirements.txt
```shell
pip install -r requirements.txt
```

### Installing packages you need individually, e.g:
```shell
pip install pandas
```

### Record packages installed on venv in requirements.txt using
```shell
pip freeze > requirements.txt
```

### Make kernel available in Jupyter
```shell
python -m ipykernel install --user --name=<<env-name>>
```

Note the above makes the kernel available regardless of what environment you run `jupyter notebook` in.

### deactivate env
```shell
deactivate
```

### List available (jupyter) kernels
```shell
jupyter kernelspec list
```

### Remove kernel
```shell
jupyter kernelspec remove <<env-name>>
```

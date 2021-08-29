In this blog post I will discuss how to get started with [Pipenv](https://pipenv.pypa.io/en/latest/) - a python packaging tool. The blog post follows Ubuntu workflow which can be easily replicated in MacOS and Windows. Let's get started.

### What is [Pipenv](https://pipenv.pypa.io/en/latest/) ?
 Pipenv is  a python packaging tool for Python and an upgrade over using [Pip](https://pip.pypa.io/en/stable/) , [Venv](https://docs.python.org/3/library/venv.html) and requirements.txt . Pipenv is a great way to combine package management with virtual environments. 

### Why do we need Package Management and Virtual environments?
According to Wlkipedia ,
>A package manager or package-management system is a collection of software tools that automates the process of installing, upgrading, configuring, and removing computer programs for a computer's operating system in a consistent manner.

A package manager automates the process of installing, uninstalling, maintaining a package. This helps developers easily manage a project's dependencies.

You can read more about package managers [here](https://en.wikipedia.org/wiki/Package_manager#Functions).

Now let's discuss virtual environments,

>A virtual environment is a self-contained directory tree that contains a Python installation for a particular version of Python, plus a number of additional packages.

A virtual environment enables us to have a specific unique python installation for each project. This prevents us from overloading the global python installation and enables us to use different versions of python for each project. 
A python virtual environment also helps segregate individual dependencies for each project and prevents code from breaking in case if any project was specifically configured to a version of Python.
You can read about virtual environments in detail [here](https://docs.python.org/3/tutorial/venv.html).

Now, that we understand what are package managers and why we need them let's get started with installation of Pipenv.

### How to install Pipenv?
To install pipenv, open a terminal window and run the following command:
```
$ pip install pipenv
```

### How to create a virtual environment using PIpenv?
Navigate into the directory you want to create a virtual environment in and open a terminal window and type the following command.
```
$ mkdir my_project
$ cd my_project/
$ pipenv install
```

### How to start a virtual environment using PIpenv?
To start a virtual environment, type the following command while being in the directory.
```
$ pipenv shell
```
 You will see a project name within parenthesis indicating we have successfully entered the required python virtual environment.

To exit the virtual environment we can type,
```
$ exit
```
### How to check the which Python installation is in active use ?

To check which python installation in use we can use the following 3 methods,

#### Method 1:
While the python shell is active type the following command,
```
$ which python
```
This will return the path of current python environment in active use.

#### Method 2:
Type this in an active python shell,
```
$ import sys
$ sys.executable
```
This will return the path of python installation in active use.

#### Method 3:
To find path of executable without activating shell following command can we used :
```
$ pipenv --venv
```


### How to install packages using Pipenv?
Type the following code to install a package usign Pipenv.
```
$ pipenv install <package-name>
```

### How to run a Python command without activating virtual environment within the current environment?
```
$ pipenv run python
```
To run a file, use the following command:
```
$ pipenv run  python <file-name>
```
### How to use requirements.txt file with Pipenv?
To install dependencies and packages using pip's requirements.txt , use the following command:
```
$ pipenv install -r <path-of-requirements.txt>
```
### How to create a requirements.txt using Pipenv?
Following command can be used to generate the content of requirements.txt :
```
$ pipenv lock -r 
```
To create a requirements.txt we can redirect this output to our requirements.txt :
```
$ pipenv lock -r > requirements.txt
```

### How to uninstall a package using Pipenv?
Following command can be used to uninstall a package using pipenv :
```
$ pipenv uninstall <package-name>
```
To uninstall all packages use `-all` flag.

### How to remove a virtual environment using Pipenv?
Following command can be used to safely remove a package using pipenv :
```
$ pipenv -rm
```

### Additional points to know about Pipenv :
1. By default, pipenv install virtual environments at `~/.local/share/virtualenvs/`.

2. To install a package that shouldn't be included in production build we can use `--dev` flag at end of install command.

3. To check security vulnerabilities in a virtual environment we can use following command :
`$ pipenv check` .

4. All dependencies of project can be tracked using following command:
`$ pipenv graph`.

---

This was first blog on pipenv and I will be writing in detail on pipenv in a few more blogs.

Do leave a thumbs up if this was helpful.
You can follow me on twitter [@raghavxk](https://twitter.com/raghavxk) to stay posted about my future blogs.
Thanks for reading!

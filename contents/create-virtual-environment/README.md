# How to create a new Virtual Environment?

Environment is a container for your application to run isolated with safely and without interrupting any other existing applications in the same machine.

Make sure you have python installed on your system.

```
python --version; pip --version
```

To create a virtual environment, you need a virtual environment manager. By default, python comes up with [venv](https://docs.python.org/3/library/venv.html) module. There are more modules like [virtualenv](https://virtualenv.pypa.io/en/latest/), etc.

In below command, using python, you are invoking `venv` module to create a new virtual environment folder with name `.venv`, in the current directory that you are in.

``` sh
python -m venv .venv
```

To activate the environment, you do the following.

``` ps
# on windows
 me@MacBook-Pro ~ .\.venv\Scripts\Activate

# on mac
 me@MacBook-Pro ~ source .venv/bin/activate

# your console will change to this
(.venv) me@MacBook-Pro ~ 
```
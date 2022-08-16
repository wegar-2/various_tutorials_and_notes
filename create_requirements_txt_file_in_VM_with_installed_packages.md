### How to create requirements.txt file in virtualenv with all currently installed packages?

Suppose that you are working in a Python virtual environment and that you have installed some packages and want to dump all of them into a ```requirements.txt``` file.

The command you need to run in your virtual environment is:


``` 
pip freeze > requirements.txt
```

What this command does is:

(1) the ```pip freeze``` generates the list of all the packages - with the information on their version

(2) the ``` > requirements.txt ``` redirects the output of ```pip freeze``` into the ```requirements.txt``` file.

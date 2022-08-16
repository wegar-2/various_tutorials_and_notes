

# How to install tensorflow for Python under MacOS?
You might expect that the commmand:

```
pip install tensorflow
```

will get you tensorflow installed under MacOS.

Alas, it won't. You need to run:

```
pip install tensorflow-metal
```

instead.

For reference, have a look at: 

<https://developer.apple.com/metal/tensorflow-plugin/>



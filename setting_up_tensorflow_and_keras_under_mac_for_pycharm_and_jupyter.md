# Setting up TensorFlow and Keras to run on MacOS + Making them work in Jupyter Notebook + solving problem with resolving TensorFlow in PyCharm


I am assuming that you already have a virtual environment setup for your project and jupyter notebook.

To install TensorFlow under MacOS run the following pip install 
commands in the terminal:

```
pip install tensorflow-macos
pip install tensorflow-metal
pip install keras
```


The working solution to the problem of PyCharm not giving you 
suggestions as you type is described 
[here](https://github.com/tensorflow/tensorflow/issues/53144): 
it boils down to changing `__init__.py` file of tensorflow.
Importantly, aside from the changes described in the linked discussion 
you will need to change one more string in the 
```__init__.py``` file: string *_keras* has to be changed to *keras* in 
one of the lines 450-500.


After you implement the steps above, you should be able to 
import `tensorflow` in Jupyter notebook.
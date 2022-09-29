# Fixing the bug *Could not identify NUMA node of platform GPU ID 0, defaulting to 0. Your kernel may not have been built with NUMA support* on MacOS


The solution of this problem on Mac is given in [this](https://developer.apple.com/forums/thread/693292) discussion.

The solution is to uninstall `tensorflow-metal` by running:

```
pip uninstall tensorflow-metal 
```


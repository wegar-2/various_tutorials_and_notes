## How to permanently set environment variable under MacOS for zrc shell?

Firstly, review the startup process of Z Shell - e.g. [here](https://tanguy.ortolo.eu/blog/article25/shrc).


Secondly, you realize that the commands listed in the ```zprofile``` file are executed when  Z Shell is the default shell of your terminal. So setting of environment variables for your terminal session (note: I am assuming here, that Z shell is your default shell, so that the ```zprofile``` script commands are performed when you start the terminal and get logged in) can be done by setting them in the ```~/.zprofile```.

#### Example
Suppose you want to set (*permanently*) a new environment variable *MY\_NEW\_ENV* to string *qwerty*.


In order to do this, add the following line to your ```.zprofile``` file (e.g. using vim):

``` export MY_NEW_ENV="qwerty" ```

save the changes, close that file and restart the *terminal* (so that the ```zprofile``` gets executed on login). Check the value of the *MY\_NEW\_ENV* environment variable by running ```echo $MY_NEW_ENV``` in the terminal. 


#### References

The following Stack Exchange [discussion](https://apple.stackexchange.com/questions/356441/how-to-add-permanent-environment-variable-in-zsh).
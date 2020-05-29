---
layout: post
---
Here is an example I install python 3.7 on Ubuntu 20.04.
In Ubuntu 20.04, python 3.8 is the main package of python. 
You could not install python 3.7 via apt-get.
So we add a server for deadsnakes packages :)

```
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt-get update
sudo apt-get install python3.7
```

Then to work mainly with python3.7, we use virtualenv for python3.7
```
virtualenv -p /usr/bin/python3.7 py37
source py37/bin/activate
```


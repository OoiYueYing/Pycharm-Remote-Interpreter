# Pycharm-Remote-Interpreter
Instructions on how to connect to a remote interpreter from Pycharm[professional edition] which allows you to run your code on a remote machine while using your local machine's Pycharm interface. The primary use case for this set-up is remote debugging.

# Installation required on remote server
virtualenvwrapper

Besides, ensure that you have SSH connection to your remote machine

# Virtual environment setup to isolate your project's environment
Assumption: our desired python version is python3.8

Perform the below on the remote machine

 Follow the command to create a new environment
 ```
which python3 # Output: /usr/bin/python3
source `which virtualenvwrapper.sh`
mkvirtualenv --python=/usr/bin/python3.8 nameOfEnvironment
 ```
 
 To enter the environment
 ```
 workon nameOfEnvironment
 ```
 
 To exit environment
 ```
 deactivate
 ```
This is the directory of where the virtual environment is stored at
```
/home/<usr>/.virtualenvs/<nameOfEnvironment>/bin/<pythonversion>
```

Link your virtual environment to your desired python version like this
```
virtualenv --python=/usr/bin/python3.8 ~/.virtualenv/<nameOfEnvironement>/
```

To run your project in the specifies virtual environment, update your python interpretor path to the following
```
/home/<usr>/.virtualenvs/<nameOfEnvironment>/bin/python3.8
```

# How to run from Pycharm

Follow this link for configuring a new remote Python interpreter via SSH credentials. This settings will help you sync your project folder immediately to the remote
server(you can choose the folder where you want to deploy your project to-only works with the default /tmp folder) and select your choice of python interpreter on the remote machine you are running on.
https://www.jetbrains.com/help/pycharm/configuring-remote-interpreters-via-ssh.html?_ga=2.111787780.1017321647.1599096644-245971671.1599096644#ssh

Next Run/Debug your application
Right-click the editor background and choose the Debug <name> 
Review the debugging output. Note that debugging actually takes place on the specified remote server.
  



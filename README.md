This tutorial is unfinished and just a draft for now, will probably update in the next few days.
This tutorial was made on Windows with PowerShell, most of the stuff will be the same if using Linux or MacOS, I will try to account for those, but no promises.
Make sure that you are using Python 3.6 or higher, you can check your python version by running ```python --version```, if you get a 2.x version running this command you can also try running ```python3 --version``` to check if you have python 3 installed alongside python 2.
# python-venv-and-Requirements.txt
A tutorial on creating a requierments.txt file for your python program

## Why use a Requirments.txt
Requirments.txt is a file that is used by pip in order to install all required packages for a program using a single command:
pip install -r requirements.txt
the -r flag stands for a requirements file, and requirements.txt is the name of said file.

This is useful if we want to install all the program dependencies in a new enviorments,
without the back and forth between (running the program) <-> (getting an error about a missing package and installing it) until all the packages have been installed.

## How to generate a Requirments.txt file for our program
pip can create the Requirments.txt file for us using: pip freeze > requirements.txt
unfortunatly the file generated will contain all the python packages on the system, and will look something like this:
```apiclient==1.0.4
beautifulsoup4==4.9.3
cachetools==4.2.1
certifi==2020.12.5
chardet==3.0.4
google==3.0.0
google-api-core==1.26.1
google-api-python-client==2.0.2
google-auth==1.27.1
google-auth-httplib2==0.1.0
google-auth-oauthlib==0.4.3
googleapis-common-protos==1.53.0
httplib2==0.19.0
idna==2.8
oauthlib==3.1.0
packaging==20.9
protobuf==3.15.6
pyasn1==0.4.8
pyasn1-modules==0.2.8
pyparsing==2.4.7
pyperclip==1.8.0
pytz==2021.1
requests==2.21.0
requests-oauthlib==1.3.0
rsa==4.7.2
selenium==3.141.0
six==1.15.0
soupsieve==2.2
tempMail2==1.0.2
uritemplate==3.0.1
urllib3==1.24.3
```

We can bypass this by following these steps:
1) Create a virtual python enviorment
2) Install the dependencies we need for our program
3) Generate our Requirments.txt file based on these dependencies

### 1. Create a python virtual enviorment
We can use the following command to set up our new virtual enviorment:
```python -m venv /path/to/new/virtual/environment```
more information here: https://docs.python.org/3/library/venv.html
After running the command you should see some files and folders created in /path/to/new/virtual/environment folder in perticular we care about the 'Scripts' folder on Windows or 'bin' on linux and MacOS.
cd into the 'Scripts' folder
and run the following command: ```.\activate```
you should now see the name of your virtual enviorment in the command line, we're now in the python virtual enviorment we've created.
lets run pip freeze > requirements.txt
If everything worked correctly this time this should generate a blank Requierments.txt
to exit the virtual enviorment we can use the command ```deactivate```.

### 2. Install the dependencies we need for our program
Now we are going to install the dependencies our program needs in that same virtual enviorment
from the virtual enviorment follow the loop described earlier:
(running the program) <-> (getting an error about a missing package and installing it)

### 3. Generate our Requirments.txt file based on these dependencies
run ```pip freeze > requirements.txt```

All done!
This is the full and minimal requierments file.

# Baal Backdoors Creators
[![MIT Licence](https://badges.frapsoft.com/os/mit/mit.png?v=103)](https://opensource.org/licenses/mit-license.php) [![](https://img.shields.io/badge/python-3.7+-blue.svg)](https://www.python.org/downloads/release/python-372/)

Baal is set of backdoors creators (i.e. factories) written in Python. This is an ethical hacker educational tool used for educational purposes only. Kindly check the code of conduct. Baal backdoors range from simple reverse shell backdoors to more complex ones.

The tool is part of an ethical hacking educational toolset which is normally taught in ethical hacking and computer security degrees or courses (please see code of conduct). 

Baal is part of a toolset of ethical hacking tools that I will publish gradually on Github.
1. Tanit Keylogger (Language: Python) - Go to [repository URL](https://github.com/HusseinBakri/Tanit-Keylogger "Tanit Keylogger").
2. Adonis ARP Spoofer (Language: Python) - Go to [repository URL](https://github.com/HusseinBakri/Adonis-ARP-Spoofer "Adonis ARP Spoofer").
3. Simple MAC Changer (Language: Python), repository URL (will be added later).
4. Anat Network Discoverer and Port Scanner (Language: Python), Go to [repository URL](https://github.com/HusseinBakri/Anat-Network-Discoverer-and-Port-Scanner).
5. Hadad Packet Sniffer (Language: Python), repository URL (will be added later).
6. Shahar DNS Spoofer (Language: Python), repository URL (will be added later).
7. Sweet Death Virus (Language: Python), repository URL (will be added later).
8. Baal Backdoors (Language: Python), **current repository**.
9. Vulnerability Scanner (Language: Python), repository URL (will be added later).

# Code of Conduct
**Launching this tool against unauthorised and unwilling users is both immoral and illegal. As am ethical white hat hacker or security specialist, your job after taking permission, is to discover vulnerabilities in programs, systems and networks or to help in discovering any gullibility in users (by social engineering). Thus, you can launch Baal or any other tool that I might publish later in this hacking series only and only when you are given explicit permission by the company that hires you or you are launching attacks against your own servers or networks. This tool is written after taking several Ethical Hacking and computer security courses. So, in other words, the code, which has a generated executable is intentionally detectable by antiviruses. It can be found in a form or another in many ethical hacking books and courses. I have added many enhancements to the tools of course. To reiterate: This is a tool written for the sole purpose of teaching you how backdoors work and it also shows you how much it is easy to write a simple, effective and yet powerful backdoor in Python. This tool is for educational purposes only and it is not meant to be used in any harmful way. To reiterate, this tool is meant to be a tool to be studied by white hat hackers and security specialists and is not meant to be deployed or used against users that do not give you explicit permission.**

# Description
Baal repository constitutes many backdoors. I will uploaded more in the future. It is kind of a factory of backdoors. 
It generates a .py backdoors and corresponding executables depending on the operating system that you are using. This tool requires **pyinstaller** to be installed on the system. **netcat.py** is a basic Python implementation of the netcat tool (nc) in the case where using netcat itself is difficult in your situation.

## Tool 1: Baal_Simple_Backdoor_Creator.py
The usage of the Baal Simple Backdoor Creator can be invoked via a -h switch.

### Using the simple backdoor without command line parameters:
```
python Baal_Simple_Backdoor_Creator.py  or ./Baal_Simple_Backdoor_Creator.py 
```
This will make the tool detect the IP of your machine i.e IP of the attacker. The tool use the default port 2233. If you want to use another port, please change accordingly. Baal_Simple_Backdoor_Creator.py in its current version use netcat on different OSs and create a netcat listener on port 2233. In a sense it uses the same commands that you would normally use on a cmd or terminal. On Linux, listening on port 2233 for connections: 
```
nc -lp 2233
```
On MacOS, listening on port 2233 for connections 
```
nc -l -p 2233
```
on Windows: To the best of my knowledge there is no built in netcat so you can use the Jon Craton nc: https://joncraton.org/blog/46/netcat-for-windows/. The Baal_Simple_Backdoor_Creator.py uses Jon Craton nc.exe found in the netcat_executables of this repo.

The Baal Simple Backdoor Creator will generate a python backdoor i.e. a very simple backdoor with .py extension. The file will be named by default as baal_s.py. The tool will also generate an executable which you can be found in the dist folder. The generated backdoor is automatically configured to connect back i.e. to reverse connect to the attacker's IP.

# Requirements
You need to install all the Python libraries required by the tools. You can install them by using pip or any other method that you are confortable with. If you wil be using pip, please check first that you have the latest version of pip and setuptools & then install the library in question
```
pip install --upgrade pip setuptools

# example wget
pip install --upgrade wget
```
Use the generated backdoors as packaged executables for your OS: Mac OS, Linux and MS Windows. You should consider using additional obfuscation techniques.

## Usage 
## Irrealistic usage (educational)
Change Backdoor_Python_FILE to the specific backdoor you want to use. To run the tool in the foreground:
```
python Backdoor_Python_FILE.py 
```
To run the tool in the background on Linux or MacOS:

```
python Backdoor_Python_FILE.py &
```
On MS Windows: you can run the tool in the background without showing a terminal/console by using pythonw.exe instead of python.exe. You can change the extension from .py to .pyw if you want.

```
pythonw Backdoor_Python_FILE.pyw
```
A better way to hide the terminal/console is elucidated in the Packaging section. The section details how to create an executable out of Baal Backdoors.

## Deployment Usage
You need to create an executable out of the backdoor in question. Kindly check the Packaging section.

# Packaging
You need the pyinstaller. You can install it via pip or pip3 or via the apt package manager.
```
pip install pyinstaller
```
A program called ***pyinstaller*** will is installed in the Python directory. On Windows, it would be an executable such as pyinstaller.exe

## Notez Bien - Antivirus won't be happy!!!
Please turn off any antivirus since the executable will be detected and the antivirus will try to delete or quarantine it. Antivirus evasion techniques is addressed in the section titled 'Avoiding antiviruses'.

## How to package as executable from Windows
To package the file as a .exe for MS Windows, move your python file(s) to a folder and run pyinstaller as follows. NB: the --onefile switch is needed especially when you have many python files. Please change the Specific_Backdoor_Python_FILE.py with the backdoor you want.

```
pyinstaller Specific_Backdoor_Python_FILE.py  --onefile
```

and 

```
pyinstaller Specific_Backdoor_Python_FILE.py  --onefile
```
Your .exe files will be found in the respective dist folders.

## How to package and run the excutable silently i.e. without showing a terminal to the user!
If you do not want the user to see a command prompt window after the .exe is run. You can add another argument called --noconsole. Please change the Specific_Backdoor_Python_FILE.py with the backdoor you want.

```
pyinstaller Specific_Backdoor_Python_FILE.py  --onefile --noconsole
```

This can work in almost all instances except when your Python code deals with standard input/output/error. 

You have to explicitly deal with standard error and standard input so per example if we have something like the following (just an example)
```
result = subprocess.check_output(command, shell=True)
```

You need to handle the 'stderr' and 'stdin' by throwing them into the Abyss!

### For Python 3
```
result = subprocess.check_output(command, shell=True, stderr=subprocess.DEVNULL, stdin=subprocess.DEVNULL )
```
### For Python 2 - you need to import the os module
```
DEVNULL = open(os.devnull, 'wb')
result = subprocess.check_output(command, shell=True, stderr=DEVNULL, stdin=DEVNULL )
```

## Create a Windows .exe executable out of a python project from a Linux OS or a Mac OS
As you know, in order to run a Windows .exe or .msi or anything similar on a Linux OS or a Mac OS, you need a program called  [wine](https://www.winehq.org/). I would assume you have installed wine on Linux per example. Go to the official Python website and download the right Python 2.7.x msi installation file or whatever version for Python 3.x.x. Navigate to the directory of the download folder of this file and then run the following command: (/i is for installing):
```
wine msiexec /i python-2.X.X.msi
```
You will get a normal installation process as you would have on any MS Windows OS, please follow the instructions to install the Python interpreter. All the programs in **Wine** are usually installed in a hidden folder called '.wine' in the Home folder of the user. So probably your Windows Python will be installed in per example ~/.wine/drive_c/Python27/. In such directory, you will find all the executables that are normally installed with any Python interpreter such as Python.exe, pip.exe etc. Navigate to this folder and run via wine the Python interpreter invoking pip in order for you to install 'pyinstaller'.

PS: wine does not access the pip modules of the Linux or MacOs so this why you need to do this.
```
cd ~/.wine/drive_c/Python27/
wine python.exe -m pip install pyinstaller
```
After the installation of of pyinstaller terminates successively, you will find the pyinstalller.exe in the Scripts directory.
To install pynput (Again, why we need to do that? as I mentioned before, you need to do that because even if this module is installed on Linux/Mac OS level, the Windows Python interpreter of wine won't be able to access it)

```
wine python.exe -m pip install pynput
```

You can then package Baal backdoors into executables:

```
wine /root/.wine/drive_c/Python27/Scripts/pyinstaller.exe  Specific_Backdoor_Python_FILE.py --onefile 
```
The binary will be stored in the dist folder.

## Creating a Mac OS executable of Baal backdoors
If you are on a Mac OS, the process is the same for installing 'pyinstaller'. First install pyinstaller through latest pip - with sudo privileges. NB: it is better to get the latest pip so to avoid errors. Please change Specific_Backdoor_Python_FILE.py with the backdoor you want.

```
sudo pip install pyinstaller
```

Then run pyinstaller on main.py

```
pyinstaller Specific_Backdoor_Python_FILE.py --onefile
```
The binary will be stored in the dist folder.

## Creating a Linux OS executable of Baal Backdoors
The process is similar to what is explained in the previous sections. Binaries can not usually be executed by just double clicking them. They need to be run from the terminal after running chmod +x in order to make them executable. 

# Enhancements/TODO
## Avoiding antiviruses
I have to mention the fact that the mere act of writing your own Hacking/Security programs with your own way of coding makes these programs unique in a way and thus undetectable by antiviruses. You will know why when I explain the main techniques used by antiviruses. Source codes and by consequence executable binaries generated out of them, are always detected when they are either too traditional or have been used by many people so they ended up as a signature in antiviruses' databases. Per instance, the code here has great parts from many sources i.e. a salad of code and this is intentional.

Now the tricks here are really a race with time for different reasons:
- 1st technique: Anti-viruses compares your program to a huge database of signatures of other malware. By huge, I mean massive. In lay terms, huge number of signatures (i.e. snippets of logic if you want) sort of database of malware logic.
- 2nd technique: This technique is used in tandem with the first technique and works as a safe guard if the signature is not found. It compares the **behaviour of your program** in real-time using a sandbox or virtual environment. The comparision involves sometimes some clever machine and deep learning algorithms. Now of course every antivirus gives this technique some sort of a brand and fancy name but it boils down to the same concepts. In nutshel, the antivisus try to figure out if your program is doing something suspicious such as opening a network port or downloading things or taking snapshots or capturing keystrokes, or connecting to a remote host vel cetera...

You sould be worried about the second technique when you want to evade antiviruses more than the first one, becuase you have literally at your disposable a trillion methods to make your program quite unique to fool an antivirus to think it is harmless and thus no signature would be matched in this way. This of course does not mean the second technique could not be defeated.

Some source code tricks (which is a big field and an art in itself so this is just a drop from the ocean):
1. Add useless code before, in-between (if possible) and after the malicious code. Add a lot of padding logic (useless loops, useless mathematical operations etc...)
2. Play with sleep patterns of your Python scripts: pausing the program and resuming it, then pausing and resuming...
3. Play with program threading such as spawning threads especially useless ones per example some weird mathematical equation calculation  in a seperate thread. This achieves amazing results!
4. Add variables that are gibberish. There are some tools that transform all your variables to shorter names or to gibberish. These types of tools are called ***'obfuscation tools'*** that fool and confuse both humans and antiviruses. Black and grey hat Hackers usually change the code of the program to the point that the padding or usefull behaviour should be far more sizable in your tool than the actual malicous code which should is normally scattered in different places of your program.
...

Some Binaries/executable tricks:
1. Changing the binaries and adding padding: this requires knowledge in **reverse enginneering and changing hex codes**. Same things you did in the source code but this time on the level of the executable or binary itself. Changing the hex codes of the .exe files per example is usually done by opening the executable in a hex editor and changing very carefully some or all of the readable sentences into something else while avoiding overwriting any usable hex code otherwise the executable will not work anymore. This usually makes the executable bypass all known anti-viruses.
2. Another easier way: Compressing the binaries or executables such as compressing the .exe via tools like UPX (https://github.com/upx/upx), a tool that compresses exe files.

Scan your .exe via tools and online services that scan your tool across different antiviruses (the famous and non famous) **WITHOUT** submitting the results to antiviruses. One service that is quite handy is called NoDistribute (https://nodistribute.com/).

Please after you are successfull in running your hacking tool that evades antiviruses, you are bound by an ethical code of conduct, so you are required both morally and legally to submit your tool and code to antiviruses databases.

### Backdoor attack that is undetectable by antiviruses
You can use an awesome tool called the Veil Framework (https://github.com/Veil-Framework/Veil). Veil generates completely undetectable backdoors to hack into computers but again you are here to learn how to create your own backdoors so there is no fun in using such frameworks! Right?

You need a Linux preferably a Kali Linux to create the backdoor using Veil. Veil requires a lot of libraries and packages to be installed. To install Veil on Linux, you need to clone the **latest** GitHub repo and from the terminal you need to cd into the config directory in the repo. There is a setup.sh script that will install all the libraries needed for the Veil Framework to work properly. Run the setup file. You can of course use the --silent switch to allow the framework to install in silent mode using the default settings. You can also use the --force switch which will overwrite any existing installation of Veil in case you were obliged to install the libraries and the framework again for whatever reason.

```./setup.sh --silent --force```

Veil is a python file that is executable. You can run from the terminal

```./Veil.py```

Make sure that you **always update Veil since your aim to evade anti-viruses**. You can update Veil from inside the framework when executed.

Veil bypasses anti-viruses by encrypting, obfuscating and padding malicious code. Recall the tricks used by black hat hackers that I have mentioned before. In the different backdoor payloads that you have, you can set the reverse IP/PORT which would be the IP of the attacker. One or two antiviruses might still detect Veil. To bypass this, I strongly advice you to play around with the options of each payload until you get something completely different and thus completely undetectable. It is advisable to try different values for the options of the payload such as the **number of processors, and the sleep in seconds** to achieve a perfect result. 

The beauty of Veil is that it generates an .exe completely undetectable if you can figure out the right otions to make your backdoor quite unique from the antiviruses' signatures-wise perspective. It also generates a source code file of the backdoor depending on the payload language that you have chosen: go, python, lua, C, C# etc….

Two other famous and powerfull tools that do the same thing as Veil framework which you might be obliged to consider in case Veil fails: The Fat Rat (https://github.com/Screetsec/TheFatRat) and the Empire project (https://github.com/EmpireProject/Empire). Both tools can generate undetectable backdoors for MacOS, Android, Linux and MS Windows.

Scan your .exe via tools and online services that scan your tool across different antiviruses (famous and non famous) **WITHOUT** submitting the results to antiviruses. One service that is quite handy is called NoDistribute (https://nodistribute.com/).

Please after you are successfull in running your hacking tool that evades antiviruses, you are bound by an ethical code of conduct, so you are required morally and legally to submit your tool and code to antiviruses databases.

# License
This program is licensed under MIT License - you are free to distribute, change, enhance and include any of the code of this application in your tools. I only expect adequate attribution and citation of this work. The attribution should include the title of the program, the author (me!) and the site or the document where the program is taken from.

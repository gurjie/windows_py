# Applocker
* Needs comments and refactoring *
* **Runs smoothly with python 3.8 in win64, but interoperability is a future work**
* Some elements of the code are not pythonic, such as the getters and setters - but that's a part of learning I suppose .This is just a personal project, mainly for learning purposes. 
* there are a unused imports too


Python GUI which invokes scheduled tasks to block/unblock files at certain times.

It does so by encrypting the files in place. 

![Sample](/Capture.PNG?raw=true "Screenie")


It follows symlinks/shortcuts to encrypt executables or whatever the target is to

Usage flow is as follows:

1) Specify target file via GUI to block access to

2) Select time to begin block, select time to restore acceess to the file

3) select frequency of block

4) Hit confirm!

5) Some bash will be executed, invoking a powershell script defining a scheduled task, populated from (safe) user input 

6) creates entries in task scheduler to execute encrypt.py and decrypt.py with the file input via GUI as argument

7) if decryption fails for some reason, which it shouldnt, run decrypt.py *filepath* to decrypt your file. It's AES 256, using a non-secret key, stored in model.py. It doesn't need to be secret

8) can't create a scheduled block more than once for the same file atm, but its a trivial fix

p.s. the git directory is a mess because i haven't changed gitignore or the dir structure at all, so don't judge :) 

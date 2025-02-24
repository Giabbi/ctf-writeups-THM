# This write up is work in progress! Come back later, and in the meantime eat some pasta (no Olive Garden Plz)
# Decryptify - Full Writeup and Walkthrough
## Challenge Description
Start the VM by clicking the Start Machine button at the top right of the task. You can complete the challenge by connecting through the VPN or the AttackBox, which contains all the essential tools.

Can you decrypt the secrets and get RCE on the system? 

## Table of Contents
- [Walkthrough](#Walkthrough)
    - [Exploring The Application](#Exploring)
    - [The API.js file](#api.js)
    - [API documentation, a dead end?](#dead-end)
    - [Enumerating with ffuf: there's hope!](#hope)
    - [Accessing the user account, first flag!](#flag1)
    - [The real decription problem](#problem)
    - [Can you hear that? It's an oracle talking! (second flag)](#flag2)
- [Acknowledgements](#acknowledgements)
- [What did we learn? (Spoiler: a lot!)](#end)
---

## Walkthrough

### Exploring The Application
Alright Amici mei, let's dive in! 
<br>
The first thing I did, as always, is running nmap on the target machine. Weirdly enough, the only thing I found was an ssh service running on port 22, meaning that just googling ```http://MACHINE_IP``` won't do anything. <br><br>
After banging my head for a while I decided to scan <b>ALL</b> the ports with 
```bash 
nmap [MACHINE_IP]1-65535 -T4
``` 
to see if I could find anything useful. After an espresso or two, it finally popped up: an http server running on port 1337 (why THM?). After going to ```http://MACHINE_IP:1337``` we can finally start the challenge.

### The API.js file
Once we land on the page, we can see two login forms, one that requires a username and an invite code, and the other requires an email instad of the username. Another interesting thing was the API documentation page, which you can find in the footer of the login page, but unfortunately this is password protected. 
<br><br>
After digging into the source code of the page I found an interesting file, API.js.
<br>[API.js file](images/API.png)<br>
The code in this file seems obfuscated, but since we don't really have anything else to work with it is worth a shot to make sense of it!
<br><br>
After looking at the code, I decided to do what any sane person would, put a few console.log statement into the file (or is should say, a copy of it I saved on my computer) and then ran it with ```node``` 
<br>
In particular, at the end a constant c is initialized by calling a bunch of functions, so I decided to print that by adding the following line to the end of the script:
```javascript
console.log(c)
```
This results in the following string:
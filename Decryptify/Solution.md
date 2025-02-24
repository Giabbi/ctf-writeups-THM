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


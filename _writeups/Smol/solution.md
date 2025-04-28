---
layout: default
title: "Smol | Walkthrough Writeup & Full Explanation"
date: 2025-04-27
banner: "assets/images/smol.png"
permalink: /writeups/smol
---

# Smol
## Challenge Description
At the heart of **Smol** is a WordPress website, a common target due to its extensive plugin ecosystem. The machine showcases a publicly known vulnerable plugin, highlighting the risks of neglecting software updates and security patches. Enhancing the learning experience, Smol introduces a backdoored plugin, emphasizing the significance of meticulous code inspection before integrating third-party components.

Quick Tips: Do you know that on computers without GPU like the AttackBox, **John The Ripper** is faster than **Hashcat**?

Questions:
- What is the user flag?
- What is the root flag?

As always, you can find the challenge at the following link: [TryHackMe Smol](https://tryhackme.com/room/smol).

## Table of Contents
- Exploring the Vulnerable Plugins
- Gaining a Foothold of the Machine - First Flag
- Escalating our privileges - Second Flag
- Takeaways: to WP or not WP

## Exploring the Vulnerable Plugins
Before we dive in, is it Christmas? It's a bit confusing (and intimidaing) to see so many hints in the description of a **medium** difficulty challenge, but hey I won't complain.

So not even starting the machine, we know already that:
- This is a vulnerable wordpress (wp) web application
- There are two vulnerable plugins:
    - One is outdated
    - The other has a backdoor

Let's go find them out!

To access this website, you'll first need to add the Machine's ip address to your `/etc/hosts` file. On linux, you can run the following command: 
```bash
sudo nano /etc/hosts
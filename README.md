# Project SECURITY - Over Ride

**Version:** 4.1

**Contact:** 42 Staff (pedaggo@staff.42.fr)

---

## Summary

This project follows the RainFall project. It will teach you how to exploit the (elf-like) binary.

---

## Table of Contents

1. [Preamble](#chapter-i-preamble)
2. [Introduction](#chapter-ii-introduction)
3. [Objectives](#chapter-iii-objectives)
4. [General Instructions](#chapter-iv-general-instructions)
5. [Mandatory Part](#chapter-v-mandatory-part)
6. [Bonus Part](#chapter-vi-bonus-part)
7. [Submission and Peer-Evaluation](#chapter-vii-submission-and-peer-evaluation)

---

## Chapter I - Preamble

### Keep Calm and Override

> There is something wrong...

This is your journey. You will need to understand the binary, exploit it, and solve the challenges. Be ready!

---

## Chapter II - Introduction

As a developer, you might have to work on software that will be used by hundreds of people.

You have learned to develop more or less complex programs without taking security into account.

With this project, you will quickly realize it's rather easy to exploit issues that can be very easily avoided.

Once you're through with this project, you will have a clearer understanding of the RAM. And this will really help you design a bugless program!

---

## Chapter III - Objectives

This project aims to further your knowledge in the world of elf-like binary exploitation in i386 system.

The more or less complex methods you will use will give you a new perspective on IT in general, but mostly raise your awareness on issues coming from programming common malpractice.

You will be challenged during this project. You have to overcome these challenges by yourself. The way you'll be dealing with these challenges must be yours and YOURS ONLY. The point is to help you develop some logic and acquire reflexes that will help you all along your career. Before asking for help, ask yourself if you have factored all the possibilities in.

---

## Chapter IV - General Instructions

- **This project will only be evaluated by humans.**

- **You may have to prove your results during the evaluation. Be ready!**

- **To make this project, you will have to use a VM (64 bits).** Once you have started your machine with the ISO provided with this subject, if your configuration is right, you will get a simple prompt with an IP:

  ```
  ╔═══════════════════════════════════════╗
  ║                                       ║
  ║   Good luck & Have fun               ║
  ║                                       ║
  ║   To start, ssh with level00/level00  ║
  ║   on 192.168.1.3:4242                ║
  ╚═══════════════════════════════════════╝
  ```

  > **💡 Tip:** If the IP address is not visible, you will get it with the command `ifconfig` once you're connected.

- **Then, you will be able to connect using the following couple of login:password: level00:level00.**

  You really should use the SSH connection available on port 4242:

  ```bash
  $ ssh level00@192.168.1.3 -p 4242
  ```

- **Once logged-in, you will have to find a way to read the ".pass" file with the "next level level0X" (X = next level number) account.**

- **This ".pass" file is located at the home root of each (level00 excluded) user.**

- **Of course, once you've reached level109 you will have to go towards the end user.**

- **Here is a session example:**

  ```
  level00@overRide:~$ ./level00 $(exploit)
  xxxxxxxxxxxxxxxxxxxxxxxx
  $ exit
  level00@overRide:~$ su level01
  Password:
  level01@overRide:~$
  ```

- **Nothing is left to chance. If there is a problem, start wondering if your code is not the cause.**

- **Using an automation tool is cheating. Cheating gets you a -42.**

- **Of course, in case of a true bug, run to the educational team!**

- **You can post your questions on the forum, Jabber, IRC, Slack...**

---

## Chapter V - Mandatory Part

- **Your repo must include anything that helped you solve each validated test.**

- **Your repository will look like this:**

  ```
  $ ls -al
  [...]
  drwxr-xr-x 2 root root 4096 Dec 3 11:11 level00
  drwxr-xr-x 2 root root 4096 Dec 3 11:11 level01
  drwxr-xr-x 2 root root 4096 Dec 3 11:11 level02
  drwxr-xr-x 2 root root 4096 Dec 3 11:11 level03
  [...]
  $ ls -alR level00
  level00:
  total 8
  drwxr-xr-x 2 root root 4096 Dec 3 15:22 .
  drwxr-xr-x 3 root root 4096 Dec 3 15:20 ..
  -rw-r--r-- 1 root root 50 Dec 3 15:22 flag
  -rw-r--r-- 1 root root 60 Dec 3 15:22 source
  -rw-r--r-- 1 root root 1 Dec 3 15:22 walkthrough
  drwxr-xr-x 2 root root 4096 Dec 3 15:22 resources

  level00/resources:
  total 8
  drwxr-xr-x 2 root root 4096 Dec 3 15:22 .
  drwxr-xr-x 2 root root 4096 Dec 3 15:22 .
  -rw-r--r-- 1 root 0 Dec 3 15:22 whatever.whatever
  $ cat level00/flag | cat -e
  xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
  $ nl level00/source
       1 #include <stdio.h>
       2 int
       3 main(void) {
       4   printf("0x4d, source\n");
       5   return (0x0);
       6 }
  $
  ```

- **You will keep everything you need to prove your results during the evaluation in the Resource folder. The flag file may be empty, but you may have to explain why.**

- **The source file must only include the exploited binary in a form any developer could understand. You're free to choose your language.**

- **The walkthrough file will include the different steps of the of the test solution.**

### ⚠️ WARNING

> You must be able to clearly and precisely explain anything that is included in the folder. The folder mustn't include ANY binary.

- **If you need to use a specific file that's included on the project's ISO, you must download it during the evaluation. You must put it in your repo under no circumstances.**

- **If you plan to use a specific external software, you must set up a specific environment (VM, docker, Vagrant).**

- **You're invited to create scripts that will make you stall, but you will have to explain them during the evaluation.**

- **For the mandatory part, you must complete the following list of levels:**

  - level100
  - level101
  - level102
  - level103
  - level104
  - level105
  - level106
  - level107
  - level108

- **During the evaluation, each member of the group must be able to justify each challenge solved:**

  > **⚠️ Hey, smarty (or not so smarty) pants! You cannot bruteforce the ssh flags. This would be useless anyway, since you will have to justify your solution during the evaluation.**

---

## Chapter VI - Bonus Part

For the bonus part, you can complete the following this last level:

- **level109**

> **ℹ️ Note:** The last user is "end". Becoming "root" is not a bonus. This is considered to be cheating.

### ⚠️ WARNING

> **The bonus part will only be assessed if the mandatory part is PERFECT. Perfect means the mandatory part has been integrally done and works without malfunctioning. If you have not passed ALL the mandatory requirements, your bonus part will not be evaluated at all.**

---

## Chapter VII - Submission and Peer-Evaluation

Turn in your assignment in your Git repository as usual. Only the work inside your repository will be evaluated during the defense. Don't hesitate to double check the names of your folders and files to ensure they are correct.

---

## Project Structure

Each level directory should contain:
- **flag** - The flag/password for the next level
- **source** - The source code or explanation of the exploit
- **walkthrough** - Step-by-step instructions to solve the challenge
- **resources/** - Any additional resources needed for the solution

---

**Good luck and have fun! 🚀**

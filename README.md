![img](assets/banner.png)

<img src='assets/htb.png' style='zoom: 80%;' align=left /> NexusPlatformer1

23rd July 2024

Prepared By: ImNullP01NT #2019566

Challenge Author(s): ImNullP01NT #2019566

Difficulty: Medium

NOTE : The headings with (!) should be necessarily included in your writeup while the ones with (*) are optional and should be included only if there is a need to. Of course, you can modify the content of each section accordingly. We just provide some boilerplate text.

# Synopsis (!)

- Briefly explain what the user must do to solve this challenge.

## Description (!)

- The challenge consists of three levels, each requiring different skills and techniques to solve. The goal is to navigate through these levels using provided hints and tools.

## Skills Required (!)

- Python
- Researching Skills
- C/C++
- Know how to use common RE tools (i.e. Ghidra, IDA)
- Hashcat
- Cheat Engine

## Skills Learned (!)

- Learn how SHA-256 cracking works.
- Learn how to manipulate game variables using Cheat Engine.
- Learn how to teleport within a game environment by modifying coordinates.

# Enumeration (!)

## Analyzing the source code (*)

- Explain what source files you are provided with when you unzip the challenge zip file.

Analyze the source files as much as you can so it is clear what the challenge is about.

...

If we look at source.py, we can see that our goal is:

- Specify the goal of the challenge (i.e. where the flag is and how it can be accessed)
- ...

The basic workflow of the script is as follows:

1. Method test() is called which then calls test1()
2. test1() creates an object of the XXX class which initializes YYY.
3. ...

A little summary of all the interesting things we have found out so far:

1. The PHP query handler does not use prepared statements.
2. The RSA modulo is generated with a non-standard way.
3. ...

# Solution (!)

## Finding the vulnerability (*)

Explain where the vulnerability is. Be as detailed as possible so there are no logical gaps as to how you figured out the vulnerability and how you will proceed to the solution.

### Level 1: Terminal Decryption

1. The password is an 8-character string that includes uppercase letters, numbers, and special characters, but no lowercase letters.
2. The position pattern provided is acababbc.

Using hashcat, the command to crack the hash is:

hashcat -a 3 -m 1400 f051d420e47f6ecaa61e344768a506bbea842baf5c1948a815bebb3d4c0aef97 -1 '?u' -2 '?d' -3 '?s' '?1?3?1?3?1?2?2?3'

### Level 2: Coin Manipulation

1. You start with 10 coins and need to reach at least 21 coins.
2. You can only add one coin at a time.

Using Cheat Engine, increment the coin count one by one, ensuring the game does not detect any sudden, unrealistic changes.

### Level 3: Teleportation in the Void

1. Open the map using the [m] key to locate the destination point.
2. Use Cheat Engine to edit the player’s coordinates to teleport to the desired location.


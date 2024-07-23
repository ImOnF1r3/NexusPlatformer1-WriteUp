![img](assets/banner.png)

<img src='assets/htb.png' style='zoom: 80%;' align=left /> NexusPlatformer1

23rd July 2024

Prepared By: ImNullP01NT #2019566

Challenge Author(s): ImNullP01NT #2019566

Difficulty: Medium

NOTE : The headings with (!) should be necessarily included in your writeup while the ones with (*) are optional and should be included only if there is a need to. Of course, you can modify the content of each section accordingly. We just provide some boilerplate text.

## Description (!)

- The challenge consists of three levels, each requiring different skills and techniques to solve. The goal is to navigate through these levels using provided hints and tools.
-  NexusPlatformer1, offers an engaging and moderately challenging experience that combines technical skills with creative problem-solving. Each level, from cracking SHA-256 hashes to manipulating game variables and teleporting through voids, is designed to test and enhance your abilities in a fun and stimulating way. The aim is to provide both an educational and enjoyable adventure that pushes the boundaries of your reverse engineering and problem-solving skills.

## Skills Required (!)

- Hashcat
- Cheat Engine

## Skills Learned (!)

- Learn how SHA-256 cracking works.
- Learn how to manipulate game variables using Cheat Engine.
- Learn how to teleport within a game environment by modifying coordinates.

# Solution (!)

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


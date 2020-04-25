---
typora-root-url: ..
---

# Bandit Level 0 → Level 1

## Level Goal

The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Commands you may need to solve this level

> ls, cd, cat, file, du, find



## solution

1. current user name

   > ![](/img/a_vulnerable/a_otw/a_bandit/a_0_1/bandit0_1.jpg)



2. List files in the home directory

   > ls
   >
   > ![ls](/img/a_vulnerable/a_otw/a_bandit/a_0_1/ls.jpg)

3. What's in **readme**

   > cat readme
   >
   > ![cat](/img/a_vulnerable/a_otw/a_bandit/a_0_1/cat.jpg)

4. And we got it

   `boJ9jbbUNNfktd78OOpsqOltutMc3MY1`

5. Finally, you can login to next level

   **`ssh bandit1@bandit.labs.overthewire.org -p 2220`**

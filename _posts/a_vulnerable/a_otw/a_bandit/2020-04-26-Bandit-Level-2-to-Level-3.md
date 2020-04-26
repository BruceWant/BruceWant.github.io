---
typora-root-url: ../../../..
---

# Bandit Level 2 → Level 3

## Level Goal

The password for the next level is stored in a file called **spaces in this filename** located in the home directory

## Commands you may need to solve this level

> ls, cd, cat, file, du, find



## solution

1. Current user name.

   > whoami
   >
   > ![whoami](/img/a_vulnerable/a_otw/a_bandit/a_2_3/whoami_2_3.jpg)

2. List the content of the home directory.

   > ls
   >
   > ![ls](/img/a_vulnerable/a_otw/a_bandit/a_2_3/ls_2_3.jpg)

3. cat the content of the `spaces in this filename` file.

   > cat **'spaces in this filename'**
   >
   > ![cat](/img/a_vulnerable/a_otw/a_bandit/a_2_3/cat_2_3.jpg)

4. We got it!

   `UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK`

5. conclusion

   > In this lab, we learned how to cat file that name has white space.

 
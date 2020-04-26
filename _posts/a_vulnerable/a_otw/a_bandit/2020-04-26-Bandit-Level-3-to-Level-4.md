---
typora-root-url: ../../../..
---

# Bandit Level 3 → Level 4

## Level Goal

The password for the next level is stored in a hidden file in the **inhere** directory.

## Commands you may need to solve this level

> ls, cd, cat, file, du, find



## solution

1. Get the current user name.

   > whoami
   >
   > ![whoami](/img/a_vulnerable/a_otw/a_bandit/a_3_4/whoami_3_4.jpg)

2. List the content of the home directory.

   > ls
   >
   > ![ls](/img/a_vulnerable/a_otw/a_bandit/a_3_4/ls_3_4.jpg)

3. Change directory to `inhere`

   > cd inhere

4. List the content of the `inhere`

   > ls -a
   >
   > ![ls](/img/a_vulnerable/a_otw/a_bandit/a_3_4/ls_a_3_4.jpg)

5. cat the content of the `.inhere`

   > cat .inhere
   >
   > ![cat](/img/a_vulnerable/a_otw/a_bandit/a_3_4/cat_3_4.jpg)

6. We got it！

   `pIwrPrtPN36QITSp3EQaw936yaFoFgAB`

7. Conclusion

   > In this lesson, we learned the argument **-a** of **ls** list the hidden file.


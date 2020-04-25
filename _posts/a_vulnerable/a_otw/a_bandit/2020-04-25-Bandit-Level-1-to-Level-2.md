---
typora-root-url: ..\..\..\..
---

# Bandit Level 1 → Level 2

## Level Goal

The password for the next level is stored in a file called **-** located in the home directory

## Commands you may need to solve this level

> ls, cd, cat, file, du, find



## solution

1. Current user name.

   > whoami
   >
   > ![whomai](/img/a_vulnerable/a_otw/a_bandit/a_1_2/whoami_1_2.jpg)

2. List the content of the home directory

   > ls
   >
   > ![ls](/img/a_vulnerable/a_otw/a_bandit/a_1_2/ls_1_2.jpg)

3. cat the content of the **-**(dash), but it failed, cat does not return.

   > cat -
   >
   > ![cat](/img/a_vulnerable/a_otw/a_bandit/a_1_2/cat_failed_1_2.jpg)
   >
   > > explanation:  Using `-` as a filename to mean stdin/stdout is a convention that a lot of programs use. It is not a special property of the filename. The kernel does not recognize `-` as special so any system calls referring to `-` as a filename will use `-` literally as the filename.
   > >
   > > With bash redirection, `-` is not recognized as a special filename, so bash will use that as the literal filename.
   > >
   > > When `cat` sees the string `-` as a filename, it treats it as a synonym for stdin. To get around this, you need to alter the string that `cat` sees in such a way that it still refers to a file called `-`. The usual way of doing this is to prefix the filename with a path - `./-`, or `/home/Tim/-`. This technique is also used to get around similar issues where command line options clash with filenames, so a file referred to as `./-e` does not appear as the `-e` command line option to a program, for example.
   > >
   > > [Reference]( https://unix.stackexchange.com/questions/16357/usage-of-dash-in-place-of-a-filename )

4. So let's do it again, with the right method.

   > cat ./-
   >
   > ![cat](/img/a_vulnerable/a_otw/a_bandit/a_1_2/cat_1_2.jpg)

5. We got it!

   `CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9`

6. Finally, you can login to next level

   **`ssh bandit2@bandit.labs.overthewire.org -p 2220`**
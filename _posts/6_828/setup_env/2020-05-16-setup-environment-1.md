# Set environment on Ubuntu 18.04 for MIT 6.828

environment: Windows 10

install virtualbox on Windows 10, install Ubuntu 18.04 on virtualbox, then compile riscv64-unknown-elf-gcc and qemu, qemu as a default preinstalled program on Ubuntu 18.04, so there

is no need to install qemu again.

1. Get riscv toolchain source code.

   `git clone --recursive https://github.com/riscv/riscv-gnu-toolchain`

   if some repository failed download, you can run the following command:

   `cd riscv-gnu-toolchain`

   `git submodule update --init --recursive`

   1.1 For example, I can't download boringssl repository, and google it, found a mirror site on github: `https://github.com/google/boringssl.git` .  this repository's local path is `./riscv-gnu-toolchain/qemu/roms/edk2/CryptoPkg/Library/OpensslLib/openssl/boringssl`

   `cd ./riscv-gnu-toolchain/qemu/roms/edk2/CryptoPkg/Library/OpensslLib/openssl/`
   
   `rm -r boringssl`
   
   `git clone https://github.com/google/boringssl.git`
   
   when successed, run the following command:
   
   `cd ./riscv-gnu-toolchain/`
   
   `git submodule update --init --recursive`
   
   If there's still some repository failed, then start step 1.1 again.

2. Prerequisites

   `sudo apt-get install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev`

3. Compile riscv tool-chain, assume that you are installing the toolchain into `/usr/local` on Ubuntu 18.04.

   `cd ./riscv-gnu-toolchain`

   `./configure --prefix=/usr/local`

   `sudo make`

   If there need some library, then you need to install it, for instance, gcc need GMP, you can go into gcc directory do this command:

`./contrib/download_prerequisities`

after this script, GMP will be ready to use. Continue with `sudo make`

4. after previous three steps, the tool-chain will be compiled successfully.

   `$ riscv64-unknown-elf-gcc --version`

   `riscv64-unknown-elf-gcc (GCC) 9.2.0
   Copyright (C) 2019 Free Software Foundation, Inc.
   This is free software; see the source for copying conditions.  There is NO
   warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.`

   `$ qemu-system-riscv64 --version`

   `QEMU emulator version 4.1.0
   Copyright (c) 2003-2019 Fabrice Bellard and the QEMU Project developers`

5. Compile and run xv6

   `cd ./xv6-riscv`

   `$ make qemu`

   `...`

   `init: starting sh`

   `$`

   if encounter this error: `qemu-system-riscv64: cannot set up guest memory 'riscv_virt_board.ram': Cannot allocate memory
   Makefile:161: recipe for target 'qemu' failed
   make: *** [qemu] Error 1`

   then you need decrease the memory from `Makefile`

   `vim Makefile`

   `/-m 3G`

   you will see this line `QEMUOPTS = -machine virt -bios none -kernel $K/kernel -m 3G -smp $(CPUS) -nographic`, change `3G` to `1.5G` and restart with `make qemu`. It will be fine, if not

   then decrease the memory size until it start successfully.

   


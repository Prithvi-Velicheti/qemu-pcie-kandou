# qemu-pcie-kandou
README for Kandou - XDPnet software test setup. 
 
## Introduction.
The goal of this setup to emulate a sample PCIe device in QEMU. Detect it using 'lspci', write a sample device driver for it.
Perform MMIO, DMA, interrupt handling etc.  

The long term goal (needs to be done) of the project is to instantiate two such devices, perform P2P DMA, test BIOS enumeration, and build enough 
capability to do software development for Eiger3. 

## System config. 
In the current setup, we are performing experiments in the qemu ARM environment on an x86 ubuntu system. 
``` 
    $ lsb_release -a
    No LSB modules are available.
    Distributor ID:	Ubuntu
    Description:	Ubuntu 24.04.3 LTS
    Release:	24.04
    Codename:	noble
 
    $ uname -a
    Linux maverick 6.14.0-37-generic #37~24.04.1-Ubuntu SMP PREEMPT_DYNAMIC Thu Nov 20 10:25:38 UTC 2 x86_64 x86_64 x86_64 GNU/Linux   
```

## Installation steps.  


### i) Clone the repo. 
```
    $ git clone git@github.com:Prithvi-Velicheti/qemu-pcie-kandou.git 
    $ cd qemu-pcie-kandou 
```
### ii) Download linux-kernel  
```
    $ wget https://ftp.riken.jp/Linux/kernel.org/linux/kernel/v6.x/linux-6.1.58.tar.xz 
    $ tar xvf linux-6.1.58.tar.xz 
    $ cd  linux-6.1.58

```
### iii) Configure and build linux kernel using the arm-gnu-toolchain provided. 
```
    $ make ARCH=arm CROSS_COMPILE=../arm-gnu-toolchain/bin/arm-none-linux-gnueabihf- defconfig 
    $ make ARCH=arm CROSS_COMPILE=../arm-gnu-toolchain/bin/arm-none-linux-gnueabihf- -j12  
    $ cd ..
         
```
          
### iv) Download  busybox. Busybox bundles essential linux commands. 

```
    $ wget https://busybox.net/downloads/busybox-1.36.1.tar.bz2
    $ tar xvf  busybox-1.36.1.tar.bz2
    $ cd busybox-1.36.1

```
### v) Configuring and building busybox.  

```
    //  Start with default config. 
    $ make ARCH=arm CROSS_COMPILE=../arm-gnu-toolchain/bin/arm-none-linux-gnueabihf- defconfig  

```
 


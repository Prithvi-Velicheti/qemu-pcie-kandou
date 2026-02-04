# qemu-pcie-kandou
README for Kandou - XDPnet software test setup. 
 
## Introduction.
The goal of this setup to emulate a sample PCIe device in QEMU. Detect it using 'lspci', write a sample device driver for it.
Perform MMIO, DMA, interrupt handling etc.  

The long term goal (needs to be done) of the project is to instantiate two such devices, perform P2P DMA, test BIOS enumeration, and build enough 
capability to do software development for Eiger3. 


## Steps



### i) Clone the repo. 
    ```
        $ git clone git@github.com:Prithvi-Velicheti/qemu-pcie-kandou.git 
        $ cd qemu-pcie-kandou 
    ```
### ii) Download linux-kernel and build it with arm-gnu-toolchain provided. 
    ```
        $ wget  
         
          


 


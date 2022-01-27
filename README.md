# lnbp21

This module source will create a new Linux kernel demodulator module with corrections for Diseqc switches. This module is part of my TechnoTrend TT-budget S2-3200 PCI card, see [wiki](https://www.linuxtv.org/wiki/index.php/STMicroelectronics_LNBP21)

Total changes from Linux sources are in separate file [ListOfChanges](ListOfChanges). 

I use it since kernel 4.x on different distribution familys (Ubuntu, Debian, Arch ,Fedora, Redhat).

## Installing:

To compile the driver, you need to have make, compiler and kernel headers installed. This module is based on kernel module replacing and is linked to others media sources of kernel, so you need first to [install](KernelInstall.md) closest kernel source for your distribtion.

Next, get the repository to local:

    git clone https://github.com/enigma131/lnbp21.git

If different kernel, you have to adjust the right path for KERNSRC and KERNELSOURCE in Makefile:

    nano lnbp21/Makefile 

If changes made, save the file then exit nano.

Initialize the DKMS structure:

    sudo dkms add ./lnbp21

Compile source / Install DKMS:

    sudo dkms install lnbp21/enigma13

Verify result :

    dkms status

    modinfo lnbp21

Reboot and test

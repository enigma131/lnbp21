# stb6100

This module source will create a new Linux kernel demodulator module with enhanced capabilities for low C/N or RF level signals. This module is part of my TechnoTrend TT-budget S2-3200 PCI card and also in other [devices](https://www.linuxtv.org/wiki/index.php/STMicroelectronics_STB6100)

Frontend tweaks (second repository [stb0899](https://github.com/enigma131/stb0899)) can also be used if included in device (my use case).

Total changes from Linux sources are in separate file [ListOfChanges](ListOfChanges). 

I use it since kernel 4.x on different distribution familys (Ubuntu, Debian, Arch ,Fedora, Redhat).

## Installing:

To compile the driver, you need to have make, compiler and kernel headers installed. This module is based on kernel module replacing and is linked to others media sources of kernel, so you need first to [install](KernelInstall.md) closest kernel source for your distribtion.

Next, get the repository to local:

    git clone https://github.com/enigma131/stb6100.git

If different kernel, you have to adjust the right path for KERNSRC and KERNELSOURCE in Makefile:

    nano stb6100/Makefile 

If changes made, save the file then exit nano.

Initialize the DKMS structure:

    sudo dkms add ./stb6100

Compile source / Install DKMS:

    sudo dkms install stb6100/enigma13

Verify result :

    dkms status

    modinfo stb6100

Reboot and test

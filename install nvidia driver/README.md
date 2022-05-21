
# How to install the NVIDIA drivers on Manjaro 21 Linux:

* The purpose of this tutorial is to install the NVIDIA drivers on Manjaro Linux. Installing the NVIDIA driver on Manjaro will increase graphic performance for your computer and enable additional features.

# Methods:
* Automatic Install using the standard Manjaro Repository.
* Manual Install using the Official nvidia.com driver.
#
## Method 1:
```console $ sudo mhwd -a pci nonfree 0300
$ sudo reboot
$ nvidia-settings 
```
#
## Method 2:
```console
$ sudo pacman -Syu

$ lspci -vnn | grep VGA

$ ls
NVIDIA-Linux-x86_64-460.67.run

$ uname -r
5.4.116-1-MANJARO

$ sudo pacman -S linux54-headers

$ sudo pacman -S base-devel dkms

In this step we will disable the default nouveau drivers. To do so we need to open and edit the /etc/default/grub Grub configuration file.Locate the line starting with GRUB_CMDLINE_LINUX and include the following code nouveau.modeset=0.

$ sudo nano /etc/default/grub

Alter the GRUB_CMDLINE_LINUX line:
GRUB_CMDLINE_LINUX="nouveau.modeset=0"

$ sudo update-grub

$ sudo reboot

$ sudo bash NVIDIA-Linux-x86_64-460.67.run

Would you like to register the kernel module sources with DKMS? This will allow DKMS to automatically build a  new module, if you install a different kernel later. ->YES 
Install NVIDIA's 32-bit compatibility libraries? -> YES
Would you like to run the nvidia-xconfig utility? -> YES 

$ sudo reboot
```
#
## Referance:
[Website Link](https://linuxconfig.org/how-to-install-the-nvidia-drivers-on-manjaro-linux)

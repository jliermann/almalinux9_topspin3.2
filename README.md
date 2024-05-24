# How to install Bruker TopSpin 3.2 on AlmaLinux 9 using VirtualBox

A collaborative manual

> [!CAUTION]
> This manual is a community effort and thus comes with no liability whatsoever. Proceed at your own risk!

## Introduction

With CentOS 7 reaching its [end of life](https://access.redhat.com/support/policy/updates/errata#Life_Cycle_Dates) on June 30th, 2024, existing Bruker NMR workstations have to be migrated to a newer distribution. However, for TopSpin 3.2 (required for Avance II spectrometers), Bruker offers [no official support](https://repo-bbio.bruker.com/AlmaLinux/9/TopSpinInstallationRequirements.html). This manual provides guidance on how to setup an NMR workstation with TopSpin 3.2 using VirtualBox.

## Prerequisites

-   A PC workstation with **x86_64bit architecture** and **two ethernet interfaces** with [AlmaLinux 9](https://almalinux.org/) installed
    -   Select **Workstation** profile during installation
    -   Admin User should be called **NMR Super User**, username `nmrsu`.
-   [VirtualBox 7.0.18](https://www.virtualbox.org/wiki/Linux_Downloads) was used for this manual
-   A CentOS 7 installation image ([download here](http://isoredirect.centos.org/centos/7/isos/x86_64/))
-   The Linux Installer for [TopSpin 3.2pl7](https://www.bruker.com/protected/de/services/software-downloads/nmr/linux.html), Bruker account is required.
-   A Bruker Avance II spectrometer (obviously)

## Preparing the Workstation

For this procedure, we used KDE Plasma Desktop, although GNOME should in principle work. To install KDE Plasma Desktop, perform the following steps (perform all commands as root):

1. Enable EPEL  
   `dnf -y install epel-release`

2. Install updates  
   `dnf -y update`

3. Enable CRB  
   `dnf config-manager --set-enabled crb`

4. Install KDE Plasma Desktop  
   `dnf -y groupinstall "KDE Plasma Workspaces"`

5. Install SDDM Desktop Manager (optional)  
   `dnf -y install sddm`

6. Enable SDDM (optional)  
   `systemctl disable gdm && systemctl enable sddm`

7. Reboot and select **Plasma** upon next login

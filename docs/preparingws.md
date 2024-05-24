# Preparing the Workstation

## Install KDE Plasma Desktop

For this procedure, we used KDE Plasma Desktop, although GNOME should in principle work. To install KDE Plasma Desktop, perform the following steps (perform all commands as root):

1. Enable EPEL  
   `dnf -y install epel-release`

2. Install updates  
   `dnf -y update`

3. Enable CRB  
   `dnf config-manager --set-enabled crb`

4. Install KDE Plasma Desktop  
   `dnf -y groupinstall "KDE Plasma Workspaces"`

5. Enable SDDM (optional)  
   `systemctl disable gdm && systemctl enable sddm`

6. Reboot and select **Plasma** upon next login

## Install VirtualBox

The easiest way to install VirtualBox is through Oracle's RPM repo.

1. Download the [RHEL repo file](https://download.virtualbox.org/virtualbox/rpm/el/virtualbox.repo) and save it as `/etc/yum.repos.d/virtualbox.repo`

2. Install VirtualBox:  
   `dnf -y update && dnf -y install VirtualBox-7.0`

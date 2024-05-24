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

Installing Arch Linux
1. Download iso from Arch Linux website. I like using a https mirror
2. Verify signature of the image by downloading the iso PGP signature from the same download page.
3. us the command `gpg --keyserver-options auto-key-retrieve --verify archlinux-version-x86_64.iso.sig` in the directory that holds both the iso file and the iso signature file. Note, the command is referring to the signature file, ensure that signature is used within the command and that the only difference between the signature file and the iso is the additional .sig extension.
4. Install balenaEtcher to flash the iso to a usb. Note, you may need to open the properties of the appimage to permit it to run as a program. This can be found by right clicking the appimage, proceeding to properties, and then to permissions.
5. Safely remove USB from computer.
6. Insert into computer you wish to install Arch onto and boot from USB. You may need to enter the BIOS options to both prioritize booting from the USB and disabling safe boot. Some safe boot options are called "Custom".
7. Save and exit the BIOS menu to proceed with the installation.
8. Your computer will boot into a terminal, you will need to ensure you have an internet connect.
9. Use the `ip link` command to list the network interfaces.
10. Set your wifi up by using the `ip link set [interface] up` command. Your interface may be called `wlan0`.
11. Scan for networks with the command `iwctl station wlan0 scan`. I'm assuming the interface is wlan0 but use whatever is appropriate.
12. Proceed with the command `iwctl station wlan0 get-networks` which will list the networks and their signal strength.
13. Use `iwctl station wlan0 connect [NetworkName]` to connect to your wifi. You may need to enter a password after this command.
14. You can now use the command `archinstall` to use the arch installer.
15. In the installer, there will be a lot of obvious choices for languages and regions. You can select what is appropriate.
16. Host name is what your computer will appear as on a network. Pick something like "codys-laptop" or "coolest-computer".
17. Setting up a root account ensures you can switch to the "superuser" account and have full access to the computer.
18. Giving an account sudo access will permit them to make root commands with a password.
19. Most things can be left as default for now.
20. ext4 is the most widely used file system.
21. I made the computer a desktop with the Xfce desktop environment for easy of use when first using. You can change the environment after the installation. Gnome and KDE are common alternatives and Wayland/Hyprland are modern but require setup and knowledge working from the terminal.
22. Additional packages you may want are: firefox, vim or neovim, htop, pulseaudio, and kitty. They can be added by typing the names in lower case and separating them with spaces.
23. Don't forget to select the Nvidia proprietary drives if you have a Nvidia GPU.
24. You should be good to install from here. It may ask you if you would like to chroot into the new installation but if you don't know what this is you can skip it.

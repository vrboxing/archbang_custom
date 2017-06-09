# Custom ArchBang Install Script
* First thing you will need is the latest ArchBang installer (https://sourceforge.net/projects/archbang/files/ArchBang-OpenRC/), I do not have anything to do with the development of ArchBang, my goal is just to make it more usable for me.
* Boot to the installer and connect to the internet
* Navigate to https://github.com/ze-angry-wombat/archbang_custom and download the zip
* Unzip the package, cd into the resulting directory, and run chmod a+x altinstall
* If you wish to edit any packages that get install you may do so, they are at the top of altinstall (nano altinstall)
* cp altinstall /usr/bin/.
* (I clean up my Downloads directory at this point as the script will re-download the zip folder)
* Then just type sudo altinstall and it will start installing apps (NOTE :: I install netctl-git to replace netcfg it will ask if you are sure you want to replace this program, I always answer yes because, if not, on first update netcfg will pull in systemd and I am aiming for a completely systemd OS here)
* After the apps, comes the actual menu for installing the system
* Go through the steps and install the system.
* Reboot and welcome to the custom ArchBang

# After reboot
* Backgrounds for the desktop can be stored in ~/.config/backgrounds, you will have to edit ~/.config/openbox/autostart to point to your new background and reboot for it to take effect.
* Menu options are stored in ~/.config/openbox/menu.xml, I have set the defaults to custom ones from the original ArchBang based on software I have installed with the script
* Guake starts as default application (this can be changed in ~/.config/openbox/autostart) by hitting F12 you can open the terminal, then type yaourt-gui, select option '1' to update your repos, and option '3' to update your system.  I couldn't update the system with the script because it wound up breaking Filesystem access everytime.
* I recommend using yaourt-gui to update your system and install software, it is a powerful tool and will make life simipler on the system (Just my opinion), to install software I always select option '9'.
* I have set Worldwide and US mirrors as the default mirrors for the build, this can be changed by editing /etc/pacman.d/mirrorlist.
* I have disabled Conky at startup because it didn't handle the transparency well with cairo-compmgr, it can be re-enabled by editing ~/.config/openbox/autostart.
* I have enabled the 'TESTING' repos in /etc/pacman.conf, if you do not wish to the use the 'TESTING' repos you may comment out those lines in that file.

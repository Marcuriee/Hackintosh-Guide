
# Booting into macOS.

* Eject the USB drive that now contains macOS Catalina installer along with an active boot loader.

* Set up your motherboard’s BIOS.

* At the BIOS screen, in the boot menu select the USB installer drive.

* Select **“Boot macOS from install macOS Catalina”** in Clover boot Menu.

* Now you will probably see verbose text, and if everything goes right you will get to the screen that states “macOS Recovery”

* Once you are greeted with the first menu, instead of choosing “Install macOS”, choose **“Start Disk Utility”**.

* Under Disk Utility, select the drive that you plan to install macOS into.

* Format this drive as **APFS** and set partition scheme to **GUID**.

* Now close Disk Utility and when you return to the Menu click on “Install macOS”.<br>
_You might run into an error saying that **“there were no packages eligible to install”**. To fix this head over-to ```utilities -> Terminal``` and then set your Date and Time properly._ 

* The installer will continue here, and should reboot at least twice. Don’t touch anything during this reboot, since Clover will automatically choose the “Preboot” volume.

* The next time the system reboots, choose boot macOS from **“Catalina SSD”** (or whatever drive you installed macOS into).

* If everything goes well, you should boot into macOS Setup.

# Transferring the Clover bootloader to your SSD/HD.

* Assuming that everything is working you should be ready to transfer the EFI folder from the EFI partition of the USB drive to the EFI partition of the SSD/HD. This is because the SSD/HD where you installed macOS into has the full operating system but can't boot without having to use the USB drive. _In order to make it, you have to copy the bootloader found in the USB drive to the EFI partition in your SSD/HD so that we can boot without having to use it._  

* So, using Clover Configurator, what you need to do is mount the EFI partition of the USB drive that you loaded macOS from, and EFI partition of the SSD/HD to which you installed macOS. Delete the EFI folder inside the SSD/HD and copy the EFI folder from the USB drive into the EFI partition in the SSD/HD. This should create a copy of the boot loader into the SSD/HD.

* Remove the USB drive and reboot your system.
* If everything went as planned, your system should boot into macOS from the SSD/HD without the USB stick.
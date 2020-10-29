## Getting iMessage, App Store, Facetime, Continuity and Other Apple Services to Work.

_Full functionality of iMessage, App Store, iTunes, Facetime and Continuity is dependent on the proper functioning of **SMBIOS, Rt Variables and System Parameters**._ The SMBIOS is essentially the identifier that is injected into macOS to specify what type of Mac your Hackintosh is. This is very important. In addition, the Mac serial number and your Ethernet adapter's hardware address (MAC-Address) is how macOS and Apple identifies your computer. The idea is to setup a Mac Serial number that is unique and therefore can be linked exclusively to your iCloud account. _Problem is that if the number that is generated is already in one of the Macs in existence somewhere, these Apple services will not work. It has to be **truly unique**._

#### TL;DR Checklist :
1. Before you begin, you must have a working Ethernet connection which is defined as **BuiltIn** and **en0**. An easy way to determine this is with the [DPCIManager app](https://github.com/MuntashirAkon/DPCIManager/releases).

<p align="center"><img src="./assets/image (80).png"></p>


If your Ethernet interface is identified as anything other than en0 you may need to reset your network configuration files.
Open Finder and browse to ```/Library/Preferences/SystemConfiguration/``` then delete these two files :

* ```NetworkInterfaces.plist```

* ```preferences.plist```

Empty the Trash and then Restart.
You may then have to add your Ethernet connection in ```System Preferences -> Network```.

---

1. In Clover Configurator, first mount the EFI partition of the boot drive.
<img src="./assets/image (81).png">

2. Go to **Rt Variables** section.
<img src="./assets/image (82).png">

3. Under the ROM section, you can leave this section to state `UseMacAddr0`. Alternatively, you can copy the MAC address of your `En0` ethernet adapter and paste it here, in all lower case, without the colons.

4. Now pay attention to the `BooterConfig` and `CsrActiveConfig`. Leave the `BooterConfig` alone.  The `CsrActiveConfig`, refers to the functionality of **SIP (System Integrity Protection)**.  SIP protects your Mac from having malicious code injected, and protects the areas most vulnerable to virus, ransomware and malware. You can Activate SIP by setting `CsrActiveConfig` to `0x00` to Deactivate SIP by setting it to `0x067`.

5. Now navigate to the **SMBIOS** section.
<img src="./assets/image (83).png">

6.Click on the arrowheads and choose the Product Name closest to what you have.

<img src="./assets/image (84).png">


7. Now, click as many times as possible on the *Generate New* button next to *Serial Number*.  The idea is to generate a serial number that fits your chosen Mac model, but is unique.

<img src="./assets/image (85).png">

_At this point I recommend that you select Trust.
Mobile appears to be selected by default and you should deselect it if you do not have a Laptop._

8. Click on *Check Coverage*, to go to the Apple Website and paste your Serial Number into the box, enter the required code and click Continue to see if that model number is associated with any known Mac.
<p align="center"><img src="./assets/image (86).png">
</p>

 _If it shows that it is a valid Mac, **Do not use this Serial Number** - Go back to Clover Configurator and generate a new one. Keep doing this again and again, until you find a serial number that is not associated with a Mac in existence._
 <br><br>

9. If you see the message "We're sorry, but this serial number is not valid. Please check your information and try again". then it is ok to use this Serial Number for your config.plist.

<p align="center"><img src="./assets/image (87).png">
</p>

_It does not mean that it is not a valid Serial Number - It means that it is not already registered. This is so important that it is worth repeating.
Once you have a unique serial number that nobody else has, click on Model Lookup to ensure that serial number does indeed correspond to the Device type you chose under product name. This is an **Extra verification step**._

10. Get back to Clover Configurator and click the Generate New button as many times as you like until you have an SmUUID number that meets with your approval.

<img src="./assets/image (88).png">

_That’s it. Save your file and reboot the system. Now you should be able to setup your iCloud account and everything should work well._
Need more help?.Check [this](https://www.youtube.com/watch?v=Qp4rMzC4O-w) out.


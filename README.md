# A GUIDE TO A VANILLA HACKINTOSH FROM SCRATCH!

## Summary

This guide was something I put together as I was trying to build a fully functional hackintosh for Programming. I am primarily a Windows user and I thought of upgrading to an iMac until I was horrified when I found the prices I would be forced to pay. After a lot of searching I managed to have a good understanding of how Hackintoshes (and macOS) works and started writing my thoughts and ideas down. After a lot of time (close to a month of tinkering) I managed to complete this project with a fully functional Hackintosh that cuts through 4K footage like butter. Quite literally everything is working perfectly. 

### Quick Terms

There's a number of terms i'll be using throughout this guide - I'll outline a few of them and their definitions here:

* _Clover_ - this is the bootloader we'll be using.  Real macs have a custom firmware that allows them to boot macOS.  PC hardware needs a little help to get this working; Clover helps us achieve that.  It also handles kext injection, ACPI renames, kext patches, and a ton of other functions.
* _Kexts_ - the word "kext" is actually the combination of **K**ernel **Ext**ension; and you can think of kexts simply as drivers for macOS.
* _Config.plist_ - this is the file that tells Clover what to do.  It's an XML formatted property list _(looks very similar to HTML)_ and is one of the most important parts of setting up your Hackintosh.

---

## My System Specs:
```
- GIGABYTE GA-Z87X-D3H Motherboard
- Intel Core i7-4790K Haswell 4.0GHz
- Sapphire Radeon RX 570
- 16GB 1600mhz DDR3 memory
- Corsair VS450 Power Supply
- 120 SSD and 1TB HD
```
--- 
# Table of contents

* [Getting Started](getting-started.md)
* [Creating The Installation Media](creating-the-installation-media.md)
* [Installing Clover](installing-clover.md)
* [Walkthrough Of Clover Configurator](walkthrough-of-clover-configurator.md)
* [Basics Of Config.plist](basics-of-config.plist.md)
* [Config.plist For Haswell](config.plist-for-haswell.md)
* [BIOS Settings](bios-settings.md)
* [Booting into macOS](booting-into-macOS.md)
* [Configuring SMBIOS](configuring-smbios.md)

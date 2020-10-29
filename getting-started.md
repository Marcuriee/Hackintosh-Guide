# Getting Started


## PreRequisites:

We'll need a few things to get us started:

1. An empty USB flash drive (8 GB or larger).
2. The Install OS X/macOS.app _(preferably downloaded directly from the app store)_
3. [Clover's Install Package](https://github.com/Dids/clover-builder/releases)
4. [Clover Configurator](http://mackie100projects.altervista.org/download-clover-configurator/) (Make sure you get the _Global_ edition)

## Kexts:
1. [FakeSMC.kext](https://bitbucket.org/RehabMan/os-x-fakesmc-kozlek/downloads/) - It emulates the SMC chip found on real macs, and convinces the OS that _yes, this is a real Mac_
2. [USBInjectAll.kext](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads/) - If you're on an H370, B360, and H310 Coffee Lake system, or an X79/X99/X299 you'll likely want to make sure to include the _XHCI-unsupported.kext_ as well.
3. For GPUs - You should grab [_WhateverGreen.kext_](https://github.com/acidanthera/WhateverGreen/releases) and the companion [_Lilu.kext_](https://github.com/vit9696/Lilu/releases) - this has the functionality of _IntelGraphicsFixup_, _NvidiaGraphicsFixup_, _CoreDisplayFixup_, and _Shiki_ all rolled into it. 
4. [IntelMausiEthernet 2.5.0](https://www.insanelymac.com/forum/files/file/396-intelmausiethernet/) - Works with most newer Intel LAN chipsets
5. [Apple ALC Sound](https://github.com/acidanthera/AppleALC/releases) -  _AppleALC_ is capable of patching _AppleHDA.kext_ on the fly to allow for native audio with unsupported codecs. It also has a number of codec verbs built in to help with audio-after-sleep.

## Extras

Depending on the rest of your hardware - you _may_ need [more kexts](https://1drv.ms/f/s!AiP7m5LaOED-m-J8-MLJGnOgAqnjGw) as well, but this guide is designed to be a general foundation, so you'll have to rely on your Google-fu for that.


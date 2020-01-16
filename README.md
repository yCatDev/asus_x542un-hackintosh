## Hackintosh for Asus x542un (Mojave/Catalina)

EFI folder and some useful stuff for installing MacOS Mojave or Catalina on Asus x542un.

### Whats working?
Almost everything for example:

- Integrated video card (Intel UHD 620)
- Audio / Microphone
- Battery status
- Built-in Web Camera
- Maybe SDCard reader (not tested)
- Bluetooth
- USB

### Whats not working?

- Touchpad (work in progress, it determineds by system but dont working)
- Wi-Fi (Atheros QCA9377)
- Discrete video card (Nvidia MX150 no driver at this time)
- Sometimes rebooting (work in progress)

## For those who want to port it on similar laptop

### About Intel UHD 620

This laptop based on Intel I7-8550u (Kaby Lake Refresh). Its **NOT KABY LAKE**
Its also has Intel UHD 620 **NOT HD 620**
So to get working video card you need to add FakePCIID.kext and FakePCIID_Intel_HD_Graphics.kext
Also main part its injecting Intel. Just add to FakeID: 0x59168086 and to platform-id: 0x59160009, **NOT 0x59160000**

### About Audio

Just add VoodooHDA.kext, CodecComander.kext and install in the system VoodooHDA_2.9.2.pkg

### About wi-fi

If you dont have opportunity to buy new Broadcom wifi card or module you can use Android USB Tethering.
MacOS must support it natively but sometimes you need custom driver so you can just install HoRNDIS-9.2.pkg and use your smartphone as wi-fi module.

### Note
Version of Clover is 4xxx. If you want to upgrade just create EFI with new version of Clover and replace her kext folder, driver folder and config.plist with my.

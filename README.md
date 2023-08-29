Yoga-720-hackintosh

# This OpenCore config work for Lenovo Yoga 720-13IKB
Intel Core i7-8550U

Based on https://github.com/dragonflylee/Yoga730-hackintosh with some changes and newer version OC

# Credits

* [OpenCore](https://github.com/acidanthera/OpenCorePkg) Boot
* [Lilu.kext](https://github.com/acidanthera/Lilu/releases/latest)
* [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake.html)

[Pre-build SSDT](https://dortania.github.io/Getting-Started-With-ACPI/ssdt-methods/ssdt-prebuilt.html#laptop-coffee-lake-8th-gen)

* [SSDT-PLUG-DRTNIA](https://github.com/dortania/Getting-Started-With-ACPI/blob/master/extra-files/decompiled/SSDT-PLUG-DRTNIA.dsl)
* [SSDT-PNLF-CFL](https://github.com/dortania/Getting-Started-With-ACPI/blob/master/extra-files/decompiled/SSDT-PNLF-CFL.dsl)
* [SSDT-XOSI](https://github.com/dortania/Getting-Started-With-ACPI/blob/master/extra-files/decompiled/SSDT-XOSI.dsl)
* [SSDT-EC-USBX-LAPTOP](https://github.com/dortania/Getting-Started-With-ACPI/blob/master/extra-files/decompiled/SSDT-EC-USBX-LAPTOP.dsl)

# What is Working

* Intel Graphic UHD620 Works fine 1536 MB, [WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen/releases/latest)
* Realtek ALC236 inject Layout-id `15` [AppleALC.kext](https://github.com/acidanthera/AppleALC/releases/latest)
* PS2 Keyboard  [VoodooPS2Controller.kext](https://github.com/acidanthera/VoodooPS2/releases/latest)
* TouchPad and TouchScreen work, [VoodooI2C.kext](https://github.com/alexandred/VoodooI2C/releases/latest). 
* Battery and cpu sensor, [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC/releases/latest).
* [BrightnessKeys.Kext](https://github.com/acidanthera/BrightnessKeys/releases/latest)
* [NVMeFix.kext](https://github.com/acidanthera/NVMeFix/releases/latest)
* [SystemProfilerMemoryFixup.kext](https://github.com/Goldfish64/SystemProfilerMemoryFixup)
* SSD Trim by `ThirdPartyDrives` Quirks
* Camera works fine
* Hibernation and wake up
* Wlan Intel Dual Band Wireless-AC 8265
* Intel Bluetooth V4.2 Module

# BIOS setting before install

* Disable Security -> Intel SGX -> Intel SGX Controller
* Disable Security -> Secure Boot
* Switch RAID to AHCI in Configuration -> SATA Controller Mode

# Misc after install

* [Enable HiDPI](https://github.com/xzhih/one-key-hidpi)
```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi.sh)"
```

I installed a macos on a free partition of a working laptop where Windows was installed. 
The OpenCore bootloader has replaced the Windows bootloader and offers a choice of systems to boot on startup. 
Both systems work well, and solve professional tasks at work. 
It is important to note the improvement in sound quality on MacOS compared to the sound in Windows. 
The AppleALC driver sounds better then ALC236 HDA.

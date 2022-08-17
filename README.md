# AsusN552-VX Hackintosh
EFI directory for Asus N552-VX based on Opencore project
### Last update
**November 2021**, MacOS Monterey update
### Last checked MacOS version
12.5
## Disclaimers
- not all the ACPI patches were made by me, so i can not guarantee security and stability for those patches, althrough i have done some tests
- this repo will be updated once per year, one month or so after the release on the newest MacOS (unless differently specified)
### PC spec
Quick pc spec to ensure hardware is the same
- CPU : Intel i7-6700hq
- dGPU: Nvidia gtx 950m

## What's not working
- dGPU : no driver are released by Apple for Nvidia cards
- sleeping in AC mode : while charging pc cannot go to sleap -> no esasy fix founded
- sd card reader : not tested
## Usage
### Recommended
**General Advise** : use this repo as a mirror to correct your mistakes during the creation of your own EFI folder
- create your own EFI directory by following the excelent Dortania's guide\
 https://dortania.github.io/OpenCore-Install-Guide/
- boot up your efi to see what is not working
- if something is not working use this provided EFI as a mirror to detect differecens and make changes accordingly
- **do not directly copy kext files** as they may be outdated and not working anymore with your Opencore version 
- during the creation of EFI folder you probably will miss trackpad and/or keyboard backligth and/or sound and/or Fn keybindigs\
**You can copy ACPI files** in your ACPI directory to fix problems\
**Waning** ACPI files alone will not fix your problems, you will have to manually add to the config.plist in ACPI/Patch the correct patches to make them work

|SSDT file |functionality|
|----------|-------------|
|ATKD|used to fix keyboard backlight in combination whit AsusSMC.kext|
|GPIO|used to enable trackpad with I2C kext|
|EC,HPET,PLUG,PNLF,USBX|see Dortania's guide|
### Discouraged
- Use the provided efi as it is to install MacOS\
**Warning** you will have to generate personal device info as stated in Dortania's guide, such as serial number\
In config.plist -> PlatformInfo

```

	<key>MLB</key>
	<string>INSERT HERE</string>
	<key>MaxBIOSVersion</key>
	<false/>
	<key>ProcessorType</key>
	<integer>0</integer>
	<key>ROM</key>
	<data>INSERT HERE</data>
	<key>SpoofVendor</key>
	<true/>
	<key>SystemMemoryStatus</key>
	<string>Auto</string>
	<key>SystemProductName</key>
	<string>MacBookPro13,3</string>
	<key>SystemSerialNumber</key>
	<string>INSERT HERE</string>
	<key>SystemUUID</key>
	<string>INSERT HERE</string>
```
---
Feel free to open up issues if you encounter some problems;\
I will answer as soon as possible.

## Hackintosh: [OpenCore 0.7.5] {Montery 12.1} Gigabyte Z590 Vision D, i9 10850k, Radeon 6900 XT, 64gb 3600mhz, WD SN850
The build at a high-level: Gigabyte Z590 Vision D, i9 10850k, Radeon 6900 XT, 64gb 3600mhz, WD SN850

_________________________________

Hardware Specifics for this build: 
```
[CPU][Intel Core i9 10850k 3.6 GHz 10-Core, 20-thread Processor]
[CPU Cooler][Corsair H115i PRO XT 280mm Rad (Dual 140mm Fans) Liquid CPU Cooler]
[Motherboard][Gigabyte Z590 Vision D Motherboard]
[Memory][G.Skill Trident Z Royal Series (2 x 32 GB) DDR4-3600 CL18 Memory]
[Storage][Western Digitial SN850 1 TB NVME] {OSX: Big Sur} 
[Storage][Samsung 970 Evo Plus 1 TB M.2-2280 NVME Solid State Drive] {Windows dedicated}
[Storage][Samsung 860 Evo 500 GB 2.5" Solid State Drive] {Ubuntu dedicated}
[Video Card][XFX Merc Radeon 69000 XT Video Card]
[Case][Corsair 680x ATX]
[Power Supply][Corsair RMx Series™ RM850x 850 Watt 80 PLUS Gold PSU]
[Wireless Network Adapter][ASUS AC68 ac1900][Moved to on-board]
[Monitor][Samsung 890 LC34H890WGNXGO 34.0" 3440x1440 100 Hz Monitor]
```
_________________________________

## Status
Important to note I'm using 10th gen i9– I have not tested 11th gen.
OpenCore 0.7.5 + Monterey 12.1
Audio works natively.
Thunderbolt works natively– nothing extra required. Not sure about some features like hot swapping.
Onboard WiFi works with AirportItlwm.kext
Onboard Bluetooth works great with the IntelBluetoothInjector.kext and IntelBluetoothFirmware.kext added.
USB Map is custom mapped / works great / important to note that USB2.0 only works on the bottom blue ports on the motherboard– I disabled all other ports for the USB mapping.

_________________________________

## Bios
Revision F5d
XHCI Handoff = Enabled
iGPU = Enabled
Serial Port = Disabled
Legacy USB Support = Disabled
X.M.P. Profile = 1

_________________________________

## Issues
The Corsair Commander Pro RGB controller (that comes with the 680X Case) does NOT play nicely with BigSur. Something about the device ID triggers OSX into thinking you're running on a UPS (Uninterrupted power supply) with 0% battery. This does not affect performance, nothing is throttled, however you're greeted login with a warning message and you can NOT run OS updates this way without the added kext bundled in this EFI which disables this service from ever starting.

Sleep- I was having issues with sleep randomly waking/crashing so sleep has been switched to only wake by pressing power button. This isn't "native", but works perfectly.

_________________________________

## Misc
I have tested a StarTech.com U.2 to PCIe Adapter for 2.5" U.2 NVMe SSDs(SFF-8639)(PEX4SFF8639) and it works great. I paired it with a Intel DC P4610 Series SSDPE2KE016T801 1.6TB U.2 drive that worked fine in Big Sur.

Additionally– I have tested a Ziyituod 4 Port SATA Controller Expansion PCIe card (Marvell 9215) (Non-Raid)(ZYT-SA3014) full with NAS drives that also worked great in Big Sur.

Replace with your serial, MLB, etc.

_________________________________

## Credits / Thanks
Special thanks to MaLd0n on the Olarila group for expertise/assist on putting this together.
Dortania guide.
OpenCore.

_________________________________


### Cheers!
:)

## Hackintosh: [OpenCore 0.8.0 // Olarila] {Monterey 12.4} Gigabyte Z590 Vision D, i9 10850k, Radeon 6900 XT, 64gb 3600mhz, WD SN850
The build at a high-level: Gigabyte Z590 Vision D, i9 10850k, Radeon 6900 XT, 64gb 3600mhz, WD SN850

_________________________________

Hardware Specifics for this build: 
```
[CPU][Intel Core i9 10850k 3.6 GHz 10-Core, 20-thread Processor]
[CPU Cooler][Corsair H115i PRO XT 280mm Rad (Dual 140mm Fans) Liquid CPU Cooler]
[Motherboard][Gigabyte Z590 Vision D Motherboard]
[Memory][G.Skill Trident Z Royal Series (2 x 32 GB) DDR4-3600 CL18 Memory]
[Storage][Western Digitial SN850 1 TB NVME] {MacOS dedicated} 
[Storage][Samsung 970 Evo Plus 1 TB M.2-2280 NVME Solid State Drive] {Windows dedicated}
[Storage][Samsung 860 Evo 500 GB 2.5" Solid State Drive] {Ubuntu dedicated}
[Video Card][XFX Merc Radeon 69000 XT Video Card]
[Case][Corsair 680x ATX]
[Power Supply][Corsair RMx Series™ RM850x 850 Watt 80 PLUS Gold PSU]
[Wireless Network Adapter][ASUS AC68 ac1900][Moved to on-board instead]
[Monitor][Samsung 890 LC34H890WGNXGO 34.0" 3440x1440 100 Hz Monitor]
```
_________________________________

## Status
Important to note I'm using 10th gen i9– I have not tested 11th gen.
OpenCore 0.8.0 + Monterey 12.4
Audio works natively.
Thunderbolt works natively– nothing extra required. Not sure about some features like hot swapping.
Onboard Ethernet is working.
Onboard WiFi works with AirportItlwm.kext
Onboard Bluetooth with the IntelBluetoothInjector.kext and BlueToolFixup.kext added– I have experienced some instabilities here.
USB Map is custom mapped / works great / important to note that USB2.0 only works on the bottom blue ports on the motherboard– I disabled all other ports for the USB mapping.
GeekBench Single-Core CPU Score: 1,260
GeekBench Multi-Core CPU Score: 11,139
GeekBench GPU Score: 121,075 

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
The Corsair Commander Pro RGB controller (that comes with the 680X Case) does NOT play nicely with BigSur/Monterey. Something about the device ID triggers OSX into thinking you're running on a UPS (Uninterrupted power supply) with 0% battery. This does not affect performance, nothing is throttled, however you're greeted login with a warning message and you can NOT run OS updates this way without the added kext bundled in this EFI which disables this service from ever starting.

I didn't have issues with sleep until I swapped over to the 6900 xt. Still need to investigate whats going on there. It isn't waking and will reboot in sleep sometimes.

_________________________________

## Misc
I have tested a StarTech.com U.2 to PCIe Adapter for 2.5" U.2 NVMe SSDs(SFF-8639)(PEX4SFF8639) and it works great. I paired it with a Intel DC P4610 Series SSDPE2KE016T801 1.6TB U.2 drive that worked fine in Big Sur.

Additionally– I have tested a Ziyituod 4 Port SATA Controller Expansion PCIe card (Marvell 9215) (Non-Raid)(ZYT-SA3014) full with NAS drives that also worked great in Big Sur.

Replace with your serial, MLB, etc.

_________________________________

## Credits / Thanks
Special thanks to MaLd0n on the Olarila group for expertise/assist on putting this together. Dortania guide. OpenCore.

_________________________________

### Cheers!
:)

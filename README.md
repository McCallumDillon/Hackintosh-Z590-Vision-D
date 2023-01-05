## Hackintosh: [OpenCore 0.8.8] {Ventura 13.1.0} Gigabyte Z590 Vision D, i9 10850k, Radeon 6900 XT, 64gb 3600mhz, WD SN850
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
Important to note I'm using 10th gen cometlake i9– I have not tested 11th gen.
OpenCore 0.8.8 + Ventura 13.1.0
Audio works.
Thunderbolt works– nothing extra required. Not sure about some features like hot swapping.
Onboard Ethernet is working (both ports).
Onboard WiFi works with AirportItlwm.kext (v2.2.0-alpha – will need to update when stable release is published)
Onboard Bluetooth works (with the added IntelBluetoothInjector.kext and BlueToolFixup.kext)
USB Map is generic– you should replace with your own custom USBMap to ensure sleep/wake functions working properly.
GeekBench5 Single-Core CPU Score: 1,260
GeekBench5 Multi-Core CPU Score: 11,139
GeekBench5 GPU Score: 125,608 

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
The Corsair Commander Pro RGB controller (that comes with the 680X Case) does NOT play nicely with OSX. Something about the device ID triggers OSX into thinking you're running on a UPS (Uninterrupted power supply) with 0% battery. This does not affect performance, nothing is throttled, however you're greeted login with a warning message and you can NOT run OS updates this way. I ran the added CommanderProFix.kext bundled in this EFI which disabled the UPS related service(s) from ever starting– this worked great up until Ventura (OSX 13.x). Most folks won't need this, but for anyone else running a Commander Pro RGB controller who stumbles across this– I will have to investigate further.

Was experiencing sleep issues + moved to wake with manual power button press in previous versions. It appears "okay" now, but will continue to monitor and see if this needs to be reintroduced. 
_________________________________

## Misc
In previous versions I was experiementing with Olarila EFIs– I have moved away from this model and now just relying on Dortania's guide for the build.

I have tested a StarTech.com U.2 to PCIe Adapter for 2.5" U.2 NVMe SSDs(SFF-8639)(PEX4SFF8639) and it works great. I paired it with a Intel DC P4610 Series SSDPE2KE016T801 1.6TB U.2 drive that worked fine.

Additionally– I have tested a Ziyituod 4 Port SATA Controller Expansion PCIe card (Marvell 9215) (Non-Raid)(ZYT-SA3014) full with NAS drives that also worked great.

Replace with your serial, MLB, etc.

_________________________________

## Credits / Thanks
Dortania guide. OpenCore. Olarila.

_________________________________

### Cheers!
:)

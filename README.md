## Hackintosh: [OpenCore 0.9.2] {Ventura 13.4.0} Gigabyte Z590 Vision D, i9 10850k, Radeon 6900 XT, 64gb 3600mhz, WD SN850
The build at a high-level: Gigabyte Z590 Vision D, i9 10850k, Radeon 6900 XT, 64gb 3600mhz, WD SN850x

_________________________________

Hardware Specifics for this build: 
```
[CPU][Intel Core i9 10850k 3.6 GHz 10-Core, 20-thread Processor]
[CPU Cooler][Corsair H115i PRO XT 280mm Rad (Dual 140mm Fans) Liquid CPU Cooler]
[Motherboard][Gigabyte Z590 Vision D Motherboard]
[Memory][64GB of G.Skill Trident Z Royal Series (2 x 32 GB) DDR4-3600 CL18 Memory]
[Storage][Western Digitial SN850x 4 TB NVME] {MacOS dedicated} 
[Storage][Sabrent Rocket 1 TB NVME Solid State Drive] {Windows dedicated}
[Storage][Samsung 870 Evo 500 GB 2.5" Solid State Drive] {Ubuntu dedicated}
[Video Card][XFX Merc Radeon 69000 XT Video Card]
[Case][Corsair 680x ATX]
[Power Supply][Corsair RMx Series™ RM850x 850 Watt 80 PLUS Gold PSU]
[Wireless & Bluetooth][BCM94360NG][Replaced original onboard unit]
[Monitor][Samsung 890 LC34H890WGNXGO 34.0" 3440x1440 100 Hz Monitor]
```
_________________________________

## Status
OpenCore 0.9.2 + Ventura 13.4.0

Works:
- Audio
- Ethernet (both ports)
- Wifi
- Bluetooth
- Thunderbolt (no hot plug)

GeekBench6 Scores
- Single-Core CPU: 1,663
- Multi-Core CPU: 9,721
- GPU: 118,581 

_________________________________

## Noteworthy + Issues
Notes:
- Thunderbolt works– nothing extra required, but note to day of publishing this update there are no easy work-arounds to enable Hot plug (hot swap). A reboot is required to detect thunderbolt devices. If Hot plug is desired– there are custom firmware modified Titan Ridge PCIe cards that enable TB2 and TB3 hot plug.
- USB Map is unique to my setup/needs– you should replace with your own custom USBMap to ensure sleep/wake functions working properly.
- Wifi & Bluetooth. Original card equipped with the motherboard was giving me issues and required excessive kexts to work and the bluetooth was still spotty. I replaced the M.2 style Wifi/Bluetooth card with this `BCM94360NG` card: https://www.amazon.com/gp/product/B0861T79QY/ and it has been since working fantastically.
- The Corsair Commander Pro RGB controller (that comes with the 680X Case) does NOT play nicely with OSX. Something about the device ID triggers OSX into thinking you're running on a UPS (Uninterrupted power supply) with 0% battery. This does not affect performance, nothing is throttled, however you're greeted login with a warning message and you can NOT run OS updates this way. I ran the added CommanderProFix.kext bundled in this EFI which disabled the UPS related service(s) from ever starting– this worked great up until Ventura (OSX 13.x). Most folks won't need this, but for anyone else running a Commander Pro RGB controller who stumbles across this– I will have to investigate further.
- Was experiencing sleep issues + moved to wake with manual power button press.
- Important to note I'm using 10th Gen Comet Lake i9– I have not tested 11th Gen + with this configuration.
- Trident Z RGB Color isn't controllable/configurable inside of OSX. 
_________________________________

## Bios
```
Bios Revision F9a (released 6.1.23) [note that DSDTs might not work on older bios versions]
X.M.P. Profile = 1
VT-d = Enabled
CSM Support = Disabled
Internal Graphics (iGPU) = Enabled
DVMT Pre-Allocated = 64M
Above 4G Decoding = Enabled
Re-Size BAR Support = Enabled
IOAPIC 24-119 Entries = Disabled
Discrete Thunderbolt(TM) Support = Enabled
Wake From Thunderbolt(TM) Devices = Disabled
Native OS security for TBT = Disabled
Thunderbolt Usb Support = Disabled
Thunderbolt Boot Support = Disabled
Titan Ridge Workaround for OSUP = Disabled
Tbt Dynamic AC/DC L1 = Disabled
GPIO3 Force Pwr = Enabled
Legacy USB Support = Disabled
XHCI Handoff = Enabled
USB Mass Storage Driver Support = Enabled
Port 60/64 Emulation = Disabled
Intel Platform Trust Technology (PTT) = Disabled
Security Device Support = Disabled
Disable Block Sid = Disabled
Windows 10 Features = Windows 10
Secure Boot = Disabled
Secure Boot Mode = Standard
```
_________________________________

## Misc
- I made this for me, my needs, my setup, etc –> I'm maintaining here for others with similar builds to compare and leverage as a jumping-off starting point. I found it super helpful to examine other's EFIs, config.plists, etc when learning OpenCore and hopefully this provides new similar hacks with something to reference, but as always it likely won't be plug-and-play and you'll need to fine-tune+tweak to your needs!
- In previous versions I was experimenting with Olarila EFIs– I have moved away from this model and now just relying on Dortania's guide for the build.
- Replace with your serial, MLB, etc.

_________________________________

## Credits / Thanks
Dortania guide, OpenCore, r/Hackintosh Paradise, @CaseyJ, @The Krazy, Olarila  

_________________________________

### Cheers!
:)

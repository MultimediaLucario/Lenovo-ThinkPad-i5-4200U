# Lenovo ThinkPad OpenCore EFI for the Intel Core i5-4**2**00U CPU

![repository-open-graph-template-sped-4200u](https://user-images.githubusercontent.com/72415505/196481503-7a208378-3e38-482c-aef7-bb32e0c764b3.png)



This is an OpenCore EFI Configuration that designed for any ThinkPad rocking an ```Intel Core i5-4200U``` to boot macOS Catalina. (Confirmed working for 10.15.7)

The SMBIOS is classed as a ```MacBook Air (13 Inch, Mid-2013)``` otherwise known as ```MacBookAir6,2```.


# ⚠️ Notice ⚠️
macOS 10.15 Catalina is the only version of macOS that is guaranteed to work at this time.

If you encounter any problems with this, leave it to issues or please push appropriate confirmed working fixes, thanks.

# So what works?

- Intel HD 4400 Graphics QE/CI
- USB Ports
- Intel Ethernet
- Audio (All Inputs & Outputs with combojack)
- Sleep and Wake
- Mini DisplayPort and Mini DisplayPort Audio
- VGA (Although I don't know about other T440's, mine just seems to work)
- CPU and IGPU Power Management
- Battery Status
- Brightness
- Function Keys (Fn) - Read Below about ThinkPadAssistant
- ClickPad and TrackPad
- Integrated Camera

# My Audio Isn't working out of the box, What do I do?

- Download [ALCPluginFix](https://github.com/AO554/ThinkPad-T440-OC-0.6.2/blob/main/ALCPlugFix.zip?raw=true)
- Extracted *ALCPlugFix* folder into Desktop.
- Open *Terminal* and enter the following commands 1by1:

```
    sudo spctl --master-disable
    sudo mkdir /usr/local/bin/
    cd desktop/ALCPlugFix
    ./install.sh
````
# Wireless?
While Intel Wireless Network is presumed to now work with a Patch from [OpenIntelWireless](https://github.com/OpenIntelWireless), I have opted for a Broadcom DW1560 on BIOS Revision 2.36.

Handoff with Bluetooth with the DW1560 works perfectly and had.. well a little trouble communicating with my iPhone. (Read below)

## Known Issues (Results may vary):

- Docking Station Audio Jack has no input support, only output because we can't use two inputs as LineIn.
- SD Card Reader (At least for me) when a card is inserted will send you into a loop of Kernel Panics until removed.
- Kernel Panic into an Instant Reboot when attempting sleep, restart or Shutdown while External Display connected on one of the Docking Station Video Ports (DisplayPort, DVI, VGA)
- No DisplayPort Audio when using the Docking Station DisplayPort
- Handoff Somewhat works, WiFi Password Sharing and Hotspots with iPhone's don't seem to function.

# Keyboard Functions - Optional 
I've just started using a tool by the name of [ThinkpadAssistant](https://github.com/MSzturc/ThinkpadAssistant) which will work perfectly with this configuration, I have confirmed myself that the ``T440p`` Sample works with this, and feel like that while this isn't in my configuration it will be handy for you to have.

# Credits to:
- OpenCore Team - [@acidanthera](https://github.com/acidanthera) - (Thanks guys!)
- u/janos_litkei on Reddit - (Thank you so much buddy)
- [@Sniki](https://github.com/Sniki) - (For the Inital 0.5.9 Configuration for the T440s as Reference)
- [@ MSzturc](https://github.com/MSzturc) - (ThinkPadAssistant Tool) 

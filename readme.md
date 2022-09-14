This is an system image for Klipper, Mainsail & Fluidd for the Bananpi M2 Zero.<br>
Ensure you BananPi has an [external 2.4gHz uFL wifi antena](https://thepihut.com/products/2-4ghz-mini-flexible-wifi-antenna-with-ufl-connector) and a [heatsink](https://thepihut.com/products/raspberry-pi-heatsink), (they get hot).
### Note:  BananaPi does not work with 3.5 Inch touchscreen, and can only be controlled by Klipper web interface.


## Easy Setup
1) Download [RPi Imager](https://downloads.raspberrypi.org/imager/imager_latest.exe) & the .img file from this repo.
   
2) Plug in your SD card into your pc, and launch RPi Imager.<br>
Operating System: custom => BPIM2Zero_Klipper_Moonraker_Fluidd.img file<br>
Storage: Your SD card
Then write.

3) Once completed, insert the SD card into the BananaPi and connect your PC to the OTG USB port on the board. (The led should blink)

4) Open Device Manager, Ports and you should see "USB Serial Device (COMX)". Note down this COM number X.
   
5) Open [PUTTY](https://www.putty.org/), and connect to the RPi on Serial with the serial line: COMX   and speed: 115200
   
6) You way have to wait a while, but you should be asked to login<br>
root psswd: positron<br>
username: positron<br>
password positron<br>

7) Run "`nmtui`" and connect to your desired wifi.
   
8) copy this into your comand line to configure your Hotspot with SSID: PositronV3  and  password: positron
```
curl https://raw.githubusercontent.com/FramingApp/BananaPi-Wifi-Positron-Armbian/master/configure | bash -s -- -a PositronV3 positron

```

9) you should be greeted by "`Wifi configuration is finished! Please reboot your Banana Pi to apply changes...`", if so, all has worked. Restart and now your BananaPi is ready to go.

<br>
Connect via the hotspot or the native Wifi, and go to [positron.local/](positron.local/)

<br>
<br>
<br>
<br>
<br>



## How Image was created



1)  follow https://3dpandme.com/2022/08/14/tutorial-banana-pi-zero-m2-klipper-install/
   but install Klipper (1), Mainsail (2), and FLUIDD (4)

2) Follow https://blog.jaimyn.dev/connect-armbian-orange-pi-without-ip/ to setup wifi access from mDNS, ie. hostname.local

3) Then I forked and modified this script https://github.com/lukicdarkoo/rpi-wifi into https://github.com/FramingApp/BananaPi-Wifi-Positron-Armbian to create the Wifi AP/Hotspot.

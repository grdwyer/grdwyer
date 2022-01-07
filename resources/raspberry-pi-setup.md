Best to setup the image using the Raspberry pi [imager](https://www.raspberrypi.org/software/operating-systems/#raspberry-pi-os-32-bit)

It's all pretty much like a normal linux system if you have a display, keyboard and mouse.  

### Headless setup
If you don't have that and want to do it remotely add a file named `ssh` to the boot partition of the sd card to enable SSH on startup. Then if you have access to the router then use ethernet to connect to the router, find the raspberry pi ip address from the router and ssh in normally. (the default username:password is pi:raspberry)  
  
If you can't use a wired connection for whatever reason you can use wifi, including using your phone's hotspot function.  
In the boot partition wifi can be setup by adding a file as `wpa_supplicant.conf`
```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
country=GB
update_config=1

network={
 ssid="<Name of your wireless LAN>"
 psk="<Password for your wireless LAN>"
}
```
  
When booted up the pi will connect to the wifi set above and ssh will be enabled. The IP of the pi can be found using `arp-scan <start_ip>-<end_ip>` with the range to search across e.g.: `arp-scan 192.168.43.2-192.168.43.254`, you'll need `sudo` for this.


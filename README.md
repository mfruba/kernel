# Installation

1. Download the code (clone it or download a zipped version)
2. Move to directory: `$ cd drivers/TL-WN722N_v2.0-Ralink/rtl8188EUS_linux_v4.3.0.8_13968.20150417`
3. Build the driver by running: `$ make`
4. Install it: `# make install`
5. Load dependent modules:

```
# modprobe lib80211
# modprobe cfg80211
```

6. Insert the module into the Linux kernel: `# insmod 8188eu.ko`

# Monitor mode

To enable monitor mode, first we need to know the name of the interface.

```
# iwconfig 
eth0      no wireless extensions.

wlan0     unassociated  Nickname:"<WIFI@REALTEK>"
          Mode:Auto  Frequency=2.412 GHz  Access Point: Not-Associated   
          Sensitivity:0/0  
          Retry:off   RTS thr:off   Fragment thr:off
          Encryption key:off
          Power Management:off
          Link Quality:0  Signal level:0  Noise level:0
          Rx invalid nwid:0  Rx invalid crypt:0  Rx invalid frag:0
          Tx excessive retries:0  Invalid misc:0   Missed beacon:0

lo        no wireless extensions.
```

With the interface name (`wlan0` in this case) we can enable monitor mode:

```
# iwconfig wlan0 mode Monitor
```

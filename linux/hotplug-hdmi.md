# HotPlug HDMI

https://howtoraspberrypi.com/raspberry-pi-hdmi-not-working/

To allow hotplug HDMI display to running linux on raspberry, edit the `/boot/config.txt` and uncomment (remove the hash sign)

```
#hdmi_force_hotplug=1
#hdmi_drive=2
```

- `hdmi_force_hotplug=1`: Forces to display through HDMI event if no HDMI screen is detected. Remember to re-comment this line if you need to display the Raspberry Pi on a different port than the HDMI.
- `hdmi_drive=2`: Trying to use HDMI mode rather than DVI mode, this allows you to solve certain sound problems.

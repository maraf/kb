# Set TimeZone
A default TimeZone on Raspbian is UTC>

## Raspbian 
Use `raspi-config` -> `Localisation Options` -> `Change Timezone`.

## Shell

Current TimeZone is a file at the `/ect/localtime`. You can check using:

```
ls -ls /etc/localtime
```

To get a list of installed TimeZones:
```
ls /usr/share/zoneinfo/
```

And for Europe:
```
ls /usr/share/zoneinfo/Europe
```

There you can find `Prague`.

### Apply selected TimeZone
When to have choosen your TimeZone, unlink current one and then link the selected one:

```
unlink /etc/localtime
ln -s /usr/share/zoneinfo/Europe/Prague /etc/localtime
```

And the result is:
```
0 lrwxrwxrwx 1 root root 33 Mar 13 17:54 /etc/localtime -> /usr/share/zoneinfo/Europe/Prague
```

## CRON
CRON doesn't use system TimeZone and you need to set it separately. One option is to edit user's crontab.
```
TZ=CET
```

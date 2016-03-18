# mercury-gpsd
GPSD Config for Mercury

Mercury is a small embedded [Foxboard LX832](http://www.acmesystems.it/FOXLX) from Acme Systems that I use to monitor power at my cottage and alert me to power outages and other small things.

For GPS functionality it uses [GPSD](http://www.catb.org/gpsd/) which provides a series of GPS utilities and tools that includes a lightweight GPS Daemon for receiving NMEA messages from an attached GPS source. [[GPSD](http://www.catb.org/gpsd/) was chosen because the Foxboard runs a **really** old version of OpenWRT, which is unfortunately the newest OS available for the now long discontinued board, and gpsd is the only GPS package available. The choice was pretty simple, although it seems GPSD is extensively used for many projects including Android.

## Initscript
The initscript `gpsd.init` is OpenWRT inspired and CrisOS focused, hence leverages a few standardised settings that are only useful to that paticular distro.

To use the initscript it should be installed in `/etc/init.d`.
```
root@host:~# cp gpsd.init /etc/init.d/gpsd
```
    
To enable GPSD to start at boot, enable it
```
root@host:~# /etc/init.d/gpsd enable
```

To start/stop/restart GPSD 
````
root@host:~# /etc/init.d/gpsd start
root@host:~# /etc/init.d/gpsd stop
root@host:~# /etc/init.d/gpsd restart
```

## Configuration
Configuration is held within `gpsd.conf` which should be installed inside `/etc`.
```
root@host:~# cp gpsd.conf /etc/gpsd.conf
```

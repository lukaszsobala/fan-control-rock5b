Fan-control 
==============

A tool to control fan speed by temperature automatically for ROCK5B.
Forked to modify the fan curve, as it made very little sense for the Radxa fan.

**CAUTION**

This tool only works with kernels tat don't use the kernel driver module (`pwm-fan`, to see if it is loaded, use `lsmod|grep pwm`, if it lists the module, this userspace script won't work).

Features
--------------
1. Control fan speed by temperature. (above 40 degrees)
2. Set fan speed manually

Build & install
==============
```shell
make package
dpkg -i fan-control*.deb
```

Usage
==============
```shell
systemctl enable fan-control
systemctl start fan-control
```
  
Configuration
==============

The location of the configuration file is `/etc/fan-control.json`. Configuration parameters:

|Parameter|Description|
|--|--|
|pwmchip|pwmchip id, 1 for auto scan|
|gpio|gpio id, 0 is default gpio |
|pwm-period|PWM period|
|temp-map|temperature configuration table|
|temp|temperature, in degrees Celsius|
|duty|duty ratio|
|duration|duration, in second|


License
===============
MIT License



Originally from: http://hintshop.ludvig.co.nz/show/persistent-names-usb-serial-devices/


Run to find vendor id
```
lusb
```


Run to find serial number

```
udevadm info -a -n /dev/ttyUSB1 | grep '{serial}' | head -n1
```


Run
```
sudo vim /etc/udev/rules.d
```

And add the following with the serial number and alias name.
```
SUBSYSTEM=="tty", ATTRS{idVendor}=="0403", ATTRS{idProduct}=="6001", ATTRS{serial}=="A6008isP", SYMLINK+="arduino"
```

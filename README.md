# rtl8832bu

This repo is base on [rtl8852au](https://github.com/lwfinger/rtl8852au.git) and support kernel 5.19

The driver supports rtl8832bu/rtl8852au chipsets.

This driver currently handles the following devices:

* UGREAN RTL8832BU with USB WLAN Adapter

### Installation instruction
##### Requirements
You will need to install "make", "gcc", "kernel headers", "kernel build essentials", and "git".

For **Ubuntu**: You can install them with the following command
```bash
sudo apt-get update
sudo apt-get install make gcc linux-headers-$(uname -r) build-essential git
```


If any of the packages above are not found check if your distro installs them like that.

##### Installation
When a USB device is plugged in, or detected at boot, this rule causes the utulity
usb_modeswitch to unload any 0bda:1a2b devices that it finds. If you have a
device with different ID, change the rule accordingly.

The build this driver, do the following:

For all distros:
```bash
git clone https://github.com/jian-yu/rtl8832bu.git
cd rtl8832bu
make
sudo make install

When you get a new kernel, you will need to rebuild the driver. Do the following:
cd rtl8832bu
git pull
make
sudo make install
```
When your kernel is updated, then do a 'git pull' and redo the make commands.


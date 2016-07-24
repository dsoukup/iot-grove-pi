# iot-grove-pi

A setup script for the [SensED IoT Pilot Program](http://thinkbigpartners.com/sensed-iot-pilot/) for use with Raspberry Pi's and Grove kits.  The script does the following:
* Updates the operating system and installed packages
* Installs the tightvncserver package (for remote VNC access)
* Installs a startup script for tightvncserver which launches two unique VNC sessions for the pi user (:1 through :2)
* Sets an initial VNC connection password of 'iot'
* Installs a script to print the hostname and ip address of the pi on boot (Grove LCD connected to one of the I2C ports)
* Clones both https://github.com/IoTDevLabs/iot-educ.git and https://github.com/DexterInd/GrovePi to the pi users home directory and installs them on the system

# Assumptions
1. The Operating System is a new install of the [Raspbian Jessie - May 2016](https://www.raspberrypi.org/downloads/raspbian/) image.
     See [the Raspberry Pi Software Guide](https://www.raspberrypi.org/learning/software-guide/quickstart/) for installation instructions.
2. The Raspberry Pi is connected to the network via wlan0 interface (manual step)
3. The network connection allows access to external sites (for git clone operations and operating system updates/package installation)
4. IP address is assigned within 30 seconds of boot (DHCP or static)

# How to download and use the script
```
cd ~pi
git clone https://github.com/dsoukup/iot-grove-pi.git
cd iot-grove-pi
./setup.sh
```
 
Reboot when the entire script finishes (it takes some time) 

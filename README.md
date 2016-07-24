# iot-grove-pi

First, you must install the Operating System [Raspbian Jessie - May 2016](https://www.raspberrypi.org/downloads/raspbian/). 

See [the Raspberry Pi Software Guide](https://www.raspberrypi.org/learning/software-guide/quickstart/) for installation instructions, or watch this video [Getting Started with NOOBS](https://vimeo.com/90518800).

After you have Raspbian installed on your Operating System, check that the following conditions are true before you can go on:
* Connect to the wireless network. (manual step)
* The network connection allows access to external sites (for git clone operations and operating system updates/package installation)
* IP address is assigned within 30 seconds of boot (DHCP or static)

Now you are ready to run the setup script for the [SensED IoT Pilot Program](http://thinkbigpartners.com/sensed-iot-pilot/) for use with Raspberry Pi's and Grove kits.  The script does the following:
* Updates the operating system and installed packages
* Installs the tightvncserver package (for remote VNC access)
* Installs a startup script for tightvncserver which launches two unique VNC sessions for the pi user (:1 through :2)
* Sets an initial VNC connection password of 'iot'
* Installs a script to print the hostname and ip address of the pi on boot (Grove LCD connected to one of the I2C ports)
* Clones both https://github.com/IoTDevLabs/iot-educ.git and https://github.com/DexterInd/GrovePi to the pi users home directory and installs them on the system

To download and use the script:
Launch the terminal.
Type the following into the terminal, pressing enter after each line.
```
git clone https://github.com/dsoukup/iot-grove-pi.git
cd iot-grove-pi
./setup.sh
```
The Pi will reboot when the entire script finishes (it takes some time)

Upon reboot, launch the terminal again.
Type the followiing into the terminal, pressing enter after each line.
```
cd ~/GrovePi/Firmware
sudo ./firware_update.sh
```
It will ask you if you want to update the firmware.  Type y and then enter.

Again, in the terminal, type the following, pressing enter after each line.
```
cd ~/GrovePi/Software/Python
sudo python setup.py install
```
Your installation is now ready for the SensED IoT Innovation Challenge!

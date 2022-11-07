# Install-OpenCV-Jetson-Nano
This script helps you to install the OpenCV-GPU 4.6.0 on your Jetson Nano with a few steps. Just clone, run, and take your time!

## Prerequisite
OpenCV 4.5.2 and above needs more memory to build the sources. You are better to enlarge the swap memory by following steps
1. ```sudo apt-get install nano dphys-swapfile && sudo reboot```  
2. then modify the ```sudo nano /sbin/dphys-swapfile``` at the line ```CONF_MAXSWAP``` to 4096
3. do the previous bullet to the```sudo nano /etc/dphys-swapfile```
4. check the swap allocation by ```free -m```. OpenCV 4.5.1 and below needs 4026, 4.5.2 and above needs 6074 kb
5. if you not sure about this step, I recommend to see the ***Enlarte memory swap*** topic at https://qengineering.eu/install-opencv-4.5-on-jetson-nano.html for more clearier explanation with figures, and then comeback to do the next following steps.

## Installation
Clone this repository
```bash
git clone https://github.com/geeksloth/install-opencv-jetson-nano.git && cd install-opencv-jetson-nano
```
[optional] If you want other version rather than ```4.6.0```, change the ```OPENCV_VERSION = "4.6.0"``` in the script before doing the next step.

Add an execution permission, run the script, and go to bed for 3 hours
```bash
sudo chmod 755 OpenCV.sh && ./OpenCV.sh
```

## Optional finalization
- reset your swap memory that you have done in the prerequisite step
- test the installation by 
```bash
python3 -c "import cv2; print(cv2.getBuildInformation()")
```
- cleaning steps:
```bash
sudo /etc/init.d/dphys-swapfile stop && sudo apt-get remove --purge dphys-swapfile && sudo rm /var/swap
```
```bash
sudo rm -rf ~/opencv && sudo rm -rf ~/opencv_contrib
```

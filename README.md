# Install-OpenCV-Jetson-Nano
This script allows you to install the OpenCV-GPU on your Jetson Nano with a single step. Just clone, run, and take your time!

# 3 basic steps
- Enlarge memory swap
OpenCV 4.5.2 and above needs more memory to build the sources. You are better to 
  - ```sudo apt-get install nano dphys-swapfile && sudo reboot```  
  - then modify the ```sudo nano /sbin/dphys-swapfile``` at the line ```CONF_MAXSWAP``` to 4096
  - do the previous bullet to the```sudo nano /etc/dphys-swapfile```
  - check the swap allocation by ```free -m```. OpenCV 4.5.1 and below needs 4026, 4.5.2 and above needs 6074 kb
  - if you not sure for this step, I recommend to see the topic ***Enlarte memory swap*** at https://qengineering.eu/install-opencv-4.5-on-jetson-nano.html for more cleary explanation with figures, and then comeback to do the next following steps.
- Clone this repository
```bash
git clone https://github.com/geeksloth/install-opencv-jetson-nano.git && cd install-opencv-jetson-nano
```
- Add an execution permission and run the script
```bash
sudo chmod 755 OpenCV.sh
./OpenCV.sh
```

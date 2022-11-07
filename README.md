# Install-OpenCV-Jetson-Nano
This script allows you to install the OpenCV-GPU on your Jetson Nano with a single step. Just clone, run, and take your time!

# 3 installation steps
1. Enlarge memory swap
OpenCV 4.5.2 and above needs more memory to build the sources. You are better to 
    1. ```sudo apt-get install nano dphys-swapfile && sudo reboot```  
    2. then modify the ```sudo nano /sbin/dphys-swapfile``` at the line ```CONF_MAXSWAP``` to 4096
    3. do the previous bullet to the```sudo nano /etc/dphys-swapfile```
    4. check the swap allocation by ```free -m```. OpenCV 4.5.1 and below needs 4026, 4.5.2 and above needs 6074 kb
    5. if you not sure about this step, I recommend to see the ***Enlarte memory swap*** topic at https://qengineering.eu/install-opencv-4.5-on-jetson-nano.html for more clearier explanation with figures, and then comeback to do the next following steps.
2. Clone this repository
```bash
git clone https://github.com/geeksloth/install-opencv-jetson-nano.git && cd install-opencv-jetson-nano
```
3. Add an execution permission, run the script, and go to bed for 3 hours
```bash
sudo chmod 755 OpenCV.sh
./OpenCV.sh
```

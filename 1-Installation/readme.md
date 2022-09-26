
## Materials Required:
+ Ubuntu Host PC
+ Jetson Xavier AGX H01
+ Type C data transmission cable

## Driver Installation:

Before installing the drivers, it is required to set the board into the Force Recovery Mode. </br>

### Force Recovery Mode:

There is a recovery button on the board, which is in the middle of three buttons. Hold the ***Reset Button*** for a second and then ***Recovery Button*** too, after a second release ***Reset Button*** and keep pressing the ***Recovery Button*** for other three seconds. This will enter to the Force Recovery Mode. </br>

![Driver1](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/1-Installation/driver1.png)

Connect Jetson Xavier AGX H01 with the Ubuntu host PC with a Type-C data transmit cable. </br>

![Driver2](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/1-Installation/driver2.png)

### Getting Started

+ **Step 1.** Download the the file [***AGX-H01-DRIVERS***](https://drive.google.com/drive/folders/1_9ZjCESUWXJb8Z6Vs3g_Z4ijUe7QZcLW?usp=sharing) from here. The required 32.7.1 drivers are shown below:
  + L4T Driver Package (BSP)
  + Sample Root Filesystem
  + H01 Driver  
+ **Step 2.** Unzip **H01_Drivers.zip** in the same file.
+ **Step 4.** Execute the command below:
```
tar xf Jetson_Linux_R32.7.1_aarch64.tbz2
cd Linux_for_tegra/rootfs
sudo tar xfp ../../Tegra_Linux_Sample-Root-Filesystem_R32.7.1_aarch64.tbz2
cd ..
sudo  ./apply_binaries.sh
```
+ **Step 5.** Copy **H01_Drivers** directory to the new directory **Linux_for_Tegra**
+ **Step 6.** Open the directory, **Linux_for_Tegra** and run the command below:
```
sudo bash flash.sh jetson-xavier mmcblk0p1
```
+ **Step 7.** The flash will be running and complete after some interval of time.

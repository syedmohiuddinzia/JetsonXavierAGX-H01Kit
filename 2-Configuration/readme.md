In __Jetson Xavier__ to disable uattended Upgrades run the following command: ```sudo nano -w /etc/apt/apt.conf.d/20auto-upgrades``` and change the file to the following,
```
APT::Periodic::Update-Package-Lists "1";
APT::Periodic::Unattended-Upgrade "0";
```
Now run the command ```sudo rm /var/lib/dpkg/lock```.</br>
Now reboot the machine.</br>

## Installation of NVIDIA SDK Manager in Host Machine 

* Download the latest NVIDIA SDK Manager from [https://developer.nvidia.com/nvidia-sdk-manager](https://developer.nvidia.com/nvidia-sdk-manager).
![1](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/2-Configuration/1.png)
* After downloading the file install he NVIDIA SDK Manager.
* Login the NVIDIA Account, If you have no account then create it from NVIDIA Sign Up page.

___NOTE:___ Connect Host Machine and Jetson Xavier through same network. It can be done as shown below and the in target maching find the ip address using command ```ifconfig``` which will be used later in NVIDIA SDK Manager to install additional softwares.
![Configuration](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/2-Configuration/configration.png)

# Installation of Jetson Software with NVIDIA SDK Manager
+ If not opened then open NVIDIA SDK Manager.

## Step 1: Set Up the Development Environment

+ From the Step 01 Development Environment window, select the following:
+ From the __Product Category__ panel, select Jetson.
+ From the __Hardware Configuration__ panel, select the host machine and target hardware in our case is __JETSON XAVIER AGX__.
+ From the __Target Operating System__ panel, select the operating system and __JetPack version__. In our case the JetPack version is ```4.6.1```.
+ From the __Additional SDKs__ panel, select the DeepStream if you want to instal, else donot select.
+ Click __Continue__ to proceed to the next step.</br>

![2](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/2-Configuration/2.png)

## Step 2: Review Components and Accept Licenses

+ From Step 02 enable the checkbox to accept the terms and conditions of the license agreements.
+ Unselect the __Jetson OS__ from __Target Components__.
+ Select Continue to proceed to the next step.

![3](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/2-Configuration/3.png)

+ Before the installation begins, SDK Manager prompts you to enter your sudo password.

![4](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/2-Configuration/4.png)


## Step 3: Installation

+ From Step 03 select __Ethernet__ connection option.
+ Write the IP address found using __NOTE__ above.
+ Write __username__ and __password__ of your __Target Machine__.
+ Click __INSTALL__ to install SDK components in Target machine.

![5](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/2-Configuration/5.png)

+ Before the installation begins, SDK Manager prompts you to enter your sudo password and then the installetion will begin.

![6](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/2-Configuration/6.png)

+ Wait for the setup to verify and then click on skip.

![7](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/2-Configuration/7.png)

+ Now the setup will install all the SDK components to target machine.

## Step 4: Finish

+ Click _Finish and Exit_ to end.

![8](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/2-Configuration/8.png)

In __Jetson Xavier__ to disable uattended Upgrades run the following command: ```sudo nano -w /etc/apt/apt.conf.d/20auto-upgrades``` and change the file to the following
```
APT::Periodic::Update-Package-Lists "1";
APT::Periodic::Unattended-Upgrade "0";
```
Now reboot the machine.

## Installation of NVIDIA SDK Manager in Host Machine 

* Download the latest NVIDIA SDK Manager from [](https://developer.nvidia.com/nvidia-sdk-manager
)
* After downloading the file install he NVIDIA SDK Manager.
* Login the NVIDIA Account, If you have no account then create it from NVIDIA Sign Up page.

___NOTE:___ Connect Host Machine and Jetson Xavier through same network. It can be done as shown below and the in target maching find the ip address using command ```ifconfig``` which will be used later in NVIDIA SDK Manager to install additional softwares. Also connect the ___HOST___ and ___TARGET___ via USB C tpye cable as connected in flashing process.

# Installation of Jetson Software with NVIDIA SDK Manager
+ If not opened then open NVIDIA SDK Manager.

## Step 1: Set Up the Development Environment

+ From the Step 01 Development Environment window, select the following:
+ From the __Product Category__ panel, select Jetson.
+ From the __Hardware Configuration__ panel, select the host machine and target hardware in our case is __JETSON XAVIER AGX__.
+ From the __Target Operating System__ panel, select the operating system and __JetPack version__. In our case the JetPack version is ```4.6.1```.
+ From the __Additional SDKs__ panel, select the DeepStream if you want to instal, else donot select.
+ Click __Continue__ to proceed to the next step.

## Step 2: Review Components and Accept Licenses

+ From Step 02 enable the checkbox to accept the terms and conditions of the license agreements.
+ Unselect the __Jetson OS__ from __Target Components__.
+ Select Continue to proceed to the next step.
+ Before the installation begins, SDK Manager prompts you to enter your sudo password.

## Step 3: Installation

+ From Step 03 select __Ethernet__ connection option.
+ Write the IP address found using __NOTE__ above.
+ Write __username__ and __password__ of your __Target Machine__.
+ Click __INSTALL__ to install SDK components in Target machine.
+ Before the installation begins, SDK Manager prompts you to enter your sudo password.
+ Wait for the setup to verify and then click on skip.
+ Now the setup will install all the SDK components to target machine.

## Step 4: Finish
+ Click _Fnish ad Exit_ to end.

sudo rm /var/lib/dpkg/lock


https://diyblindguy.com/tip-disable-unattended-upgrades-on-ubuntu-18-04-server/

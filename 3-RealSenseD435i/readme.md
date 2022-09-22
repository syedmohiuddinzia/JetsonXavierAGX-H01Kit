### NOTE: 
This setup was performed on JetSon Xavier AGX H01 Dev. Kit.

# Intel RealSense D435i on NVIDIA Jetson AGX Xavier

This camera includes a built in Inertial Measurement Unit (IMU). Adding an IMU allows your application to refine its depth awareness in any situation where the camera moves. This opens the door for rudimentary SLAM and tracking applications allowing better point-cloud alignment. It also allows improved environmental awareness for robotics and drones. The use of an IMU makes registration and calibration easier for handheld scanning system use cases and is also important in fields such as virtual/augmented reality and drones. When using the D435i, our Intel RealSense SDK 2.0 provides IMU data that is time stamped to align with our high quality depth data.

![d435i](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/3-RealSenseD435i/d435i.jpg)

## Inertial Measurement Unit (IMU)
The IMU is used for the detection of movements and rotations in 6 degrees of freedom (6DoF). An IMU combines a variety of sensors with gyroscopes to detect both rotation and movement in 3 axes, as well as pitch, yaw and roll. It is used in applications such as gaming and pointing devices as well as image stabilization.

![IMU](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/3-RealSenseD435i/imu.png)

## Background
The software drivers to interface with the D435i have seen a few updates (such as better CUDA support) since that time. However, the biggest challenge in installing full librealsense 2 support on the Xavier is that additional kernel modules must be built and installed. Because some of the affected modules are built in to the kernel itself, the kernel image itself should be built.</br>
The Jetson AGX Xavier is an embedded system. In this implementation, the Linux kernel is signed and resides in a partition on disk. This is for security reasons, as you are aware if you have been following the computer news for the last few months. This complicates building the kernel on the Jetson Xavier itself, as the signing application only runs on a PC. The JetPack installer contains the signing application.</br>
The NVIDIA approved method is to cross compile the kernel and modules on the PC, and then flash them on the Jetson. In this article, we do something exactly unlike that.</br>

## Librealsense 2 Installation
This installation is for intermediate and advanced developers. It is strongly suggested that you do this on a fresh install, immediately after flashing the Jetson.</br>
Clone and open repository named [buildLibrealsense2Xavier](https://github.com/jetsonhacks/buildLibrealsense2Xavier).
```bash
cd $HOME
git clone https://github.com/jetsonhacks/buildLibrealsense2Xavier
cd buildLibrealsense2Xavier
```

## Build Kernel & Modules
The first step is to build the needed modules and a new kernel. Also, in order to have the Xavier understand the different video formats, there are some patches to apply to the module source code.</br>
There are no librealsense 2 patches available to directly patch the Xavier, because it is running kernel version 4.9. This is between the different kernel versions which have patch revisions. For this reason, the patches sub-directory contains artisan patches, exquisitely crafted to upgrade the Jetson Xavier to run the librealsense 2 libraries.</br>
Some of the patches actually change header files which touch some modules which are built in to the kernel. That is why the kernel Image needs to be updated. If the kernel Image is not updated, the logs get cluttered with a large number of warnings about incorrect video formats being present.</br>
In order to patch and rebuild the kernel Image, modules and then install the modules:
```bash
./buildPatchedKernel.sh
```
At the end of the process, you should have an ‘Image’ file in the image sub-directory.

## Build librealsense 2
The machine has just rebooted. Open a terminal and go back to the repository directory.
```bash
cd buildLibrealsense2Xavier
```
Make sure there are no RealSense cameras attached to the Xavier. Now build librealsense 2, and install the libraries and applications:
```bash
./installLibrealsense.sh
```
The script compiles the library, examples and tools:
+ The library is installed in /usr/local/lib
+ The header files are in /usr/local/include
+ The examples and tools are located in /usr/local/bin
The script also sets up a udev rule so that the RealSense camera is available in user space.

Once the library is installed, plug the camera into the Jetson, or into the Jetson through a powered USB 3.0 hub. You can then execute the tools and examples, such as:
```bash
cd /usr/local/bin
./realsense-viewer
```

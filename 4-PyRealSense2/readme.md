# PyRealSense2
The python wrapper for Intel RealSense SDK 2.0 provides the C++ to Python binding required to access the SDK. This library is used for accessing Intel RealSenseTM cameras
The first issue with using the camera with the NVIDIA board arises with the lack of pre-built binary distributions of the RealSense SDK. Because the Jetson board is based on an ARM chipset (AARCH64) the SDK provided by Intel has to be built from source on the device itself.</br>

## Dependenciy
Run the following command to install the dependency
```bash
sudo apt install libssl-dev
```

## Installation
Afer installing the dependency, downloading the source, unzipping and creating the build directory
```bash
wget https://github.com/IntelRealSense/librealsense/archive/refs/tags/v2.48.0.zip
unzip v2.48.0.zip
cd librealsense-2.48.0
mkdir build && cd build
```
Setting some PATH environment variables to aware the build script where CUDA is located
```bash
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/lib64:/usr/local/cuda/extras/CUPTI/lib64
export PATH=$PATH:$CUDA_HOME/bin
```
Trying a simple build as a test if build is likely to succeed
```bash
cmake ../ -DFORCE_RSUSB_BACKEND=ON -DBUILD_PYTHON_BINDINGS:bool=true -DPYTHON_EXECUTABLE=/usr/bin/python3
```
If build succeeds then triying a more advanced build, which builds the example programs and includes optimizations such as building with CUDA support for faster alignment processing on devices such as the Jetson, which include an NVIDIA GPUs.
```bash
cmake ../ -DFORCE_RSUSB_BACKEND=ON -DBUILD_PYTHON_BINDINGS:bool=true -DPYTHON_EXECUTABLE=/usr/bin/python3 -DCMAKE_BUILD_TYPE=release -DBUILD_EXAMPLES=true -DBUILD_GRAPHICAL_EXAMPLES=true -DBUILD_WITH_CUDA:bool=true
```
If the build is successful then install
```bash
make -j4
sudo make install
```
Now pyrealsense2 should be installed, but there are still two errors that might come up.

## Resolving Permission problem

Even the module can be imported but there is still problem accessing the camera. This can be fixed by adding the rules provided in the SDK’s sources.
```
sudo cp config/99-realsense-libusb.rules /etc/udev/rules.d/
sudo udevadm control --reload-rules && udevadm trigger
```
After rebooting system the rules will be applied and now you can find your realsense device with the following command.
```
rs-enumerate-devices
```

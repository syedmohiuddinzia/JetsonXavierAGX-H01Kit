# Installation of Dlib and Face Recognition Python Library

This will help you to install Dlib and face recognition libraries on the NVIDIA Jetson Xavier AGX H01. This are foundation libraries we need for machine learning, deep neural networks and deep learning.

#### Update the packages
```bash
sudo apt-get update
```
The above command fetches the latest version of the package list from your distro's software repository, and any third-party repositories you may have configured. In other words, it will figure out what the latest version of each package and dependency is, but will not actually download or install any of those updates.

#### Install the dependencies
```bash
sudo apt-get install cmake libopenblas-dev lib liblapack-dev libjpeg-dev 
```

#### Get into Downloads Directory
```bash
cd ~/Downloads
```

#### Download [http://dlib.net/files/dlib-19.17.tar.bz2](http://dlib.net/files/dlib-19.17.tar.bz2)
```bash
wget http://dlib.net/files/dlib-19.17.tar.bz2
```

#### Unzip _(dlib.net/files/dlib-19.17.tar.bz2_
```bash
tar jxvf dlib-19.17.tar.bz2
```

#### Get into the _dlib-19.17_ folder
```bash
cd dlib-19.17
```

##### 1. open ```dlib/cuda/cudnn_dlibapi.cpp```
![dlib1](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/5-LibrariesFaceRecognitionIdentification/dlib1.png)
##### 2. Search for ```forward_algo``` in the code
##### 3. After finding comment this line
![dlib2](https://github.com/syedmohiuddinzia/JetsonXavierAGX-H01Kit/blob/main/5-LibrariesFaceRecognitionIdentification/dlib2.png)
##### 4. After commenting save the code and exit.


#### Again get into Downloads Directory
```bash
cd ~/Downloads
```

#### Again get into the _dlib-19.17_ folder
```bash
cd dlib-19.17
```

#### Install _Setup.py_ 
```bash
sudo python3 setup.py install
```

### Install Face Recognition Library
```bash
sudo pip3 install face_recognition
```
+ ___restart the terminal___



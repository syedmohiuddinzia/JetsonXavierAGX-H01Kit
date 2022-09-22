# Object Detection YoloV5 - D435i
YOLOv5 rocket is a family of object detection architectures and models pretrained on the COCO dataset, and represents Ultralytics open-source research into future vision AI methods, incorporating lessons learned and best practices evolved over thousands of hours of research and development.</br>
YoloV5 default model is trained for 79 different classes and we will use it for object detection with jetson Xavier AGX H01 Kit using RealSense D435i.</br>

```bash
pip3 install -U PyYAML==5.3.1
```

```bash
pip3 install tqdm
```

```bash
pip3 install cython
```

```bash
pip3 install -U numpy==1.19.5
```

```bash
sudo apt install build-essential libssl-dev libffi-dev python3-dev
```

```bash
pip3 install cycler==0.10
```

```bash
pip3 install kiwisolver==1.3.1
```

```bash
pip3 install pyparsing==2.4.7
```

```bash
pip3 install python-dateutil==2.8.2
```

```bash
sudo apt install libfreetype6-dev
```

```bash
pip3 install --no-deps matplotlib==3.2.2
```

```bash
sudo apt install gfortan
```

```bash
sudo apt install libopenblas-dev
```

```bash
sudo apt install libpack-dev
```

```bash
pip3 install scipy==1.4.1
```

```bash
sudo apt install libjpeg-dev
```

```bash
pip3 install pillow==8.3.2
```

```bash
wget https://nvidia.box.com/shared/static/p57jwntv436lfrd78inwl7iml6p13fzh.whl -O https://nvidia.box.com/shared/static/h1z9sw4bb1ybi0rm3tu8qdj8hs05ljbm.whl
```

```bash
pip3 install typing-extensions==3.10.0.2
```

```bash
pip3 install torch-1.9.0-cp36-cp36m-linux_aarch64.whl
```

```bash
sudo apt-get install python3-pip libopenblas-base libopenmpi-dev libomp-dev
```

```bash
git clone --branch v0.9.0 https://github.com/pytorch/vision torchvision
```

```bash
cd torchvision
```

```bash
export BUILD_VERSION=0.9.0
```

```bash
python3 setup.py install --user

```

```bash
cd ../

```

```bash
pip3 install --no-deps seaborn==0.11.0
```

```bash
pip3 install --no-deps seaborn==0.11.0
```

Download ___YoloV5 for RealSense___ from [YoloV5RealSense](https://drive.google.com/drive/folders/16Bqbsb9a1tRlVe3Zy7vM7_OBRQy4t1pg?usp=sharing)


```bash
python3 detect.py --source data/images --weights yolov5s.pt --img 648
```

```bash
git clone https://github.com/jetsonhacks/installRealSenseSDK
```

```bash
cd installRealSenseSDK/
```

```bash
./buildLibrealsense.sh
```

Open <p style='color:red'>.bashrc</p> and paste ```export PYTHONPATH=/usr/local/lib/python3.6/pyrealsense2``` at the bottom of the the file.

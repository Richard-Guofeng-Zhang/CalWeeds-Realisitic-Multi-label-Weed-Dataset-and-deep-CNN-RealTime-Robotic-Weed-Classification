# CalWeeds: a large realistic weed dataset and multi-label classification between plants and weeds #
This repository makes available the source code and public dataset for our work, "Deep-CNN based Real-Time Robotic Multi-Class Weed Identification" submitted to Internation Conference on Intelligent Robots and Systems (IROS) 2021. 

Here, our first contribution is the first adequately large image dataset CalWeeds (one/multiple kinds of weeds in one image), a library of 7702 annotated images taken from 16 different locations including 11 most common weeds in fields and gardens in California and Central China. Second, we provide a thorough pipeline from training these models with maximum efficiency to deploying the TensorRT-optimized model onto a single board computer. Third, we employ our own autonomous mobile robot and demonstrate real-time weed detection. Based on CalWeeds dataset and the pipeline, we present a baseline for classification performance using the benchmark deep learning models: DenseNet121, InceptionV3, MobileNetV2, ResNet50, and Xception. Among them, MobileNetV2, with both the shortest inference time and lowest memory consumption, is the most competitive candidate for real-time applications.

## Download the dataset images and our trained models ##
Single and negative class_image: https://drive.google.com/drive/folders/1rmvun2wcleDq5fFYR8nA83j6hiHWG9Jz?usp=sharing. 

Multiple_label_image: https://drive.google.com/drive/folders/16cZXH28BAW3lrDxtvSNPjo_z7UZvAYoA?usp=sharing.

Please git clone this repo, and create a directory called img here. 
After downloading these two groups of images, please take all images out of each subdirectory, and move all these images together to the img directory we just created. Note that img directory should contain only images. Also, please make sure all images exist in the img to correspond to csv labels.

## Environment prepartion ##
In this part, we provide detailed instructions on how to settle environment on both Nvidia platform using command line and on linux or windows using anaconda. 
Please check the requirement.txt. If you have satisfied all environments listed, you can skip this part.

### Environment installation (TensorRT supported) on Nvidia platform ###
Firstly, if the embedded system has not been flashed yet, please flash the system based on images on Nvidia. Please make sure the flashed images support the environment listed.
Particularly, for Nvidia Jetson platform, please flash with Jetpack4.3.
We can follow the following command to install the environment needed on most Nvidia platforms. 

```bash
sudo apt-get install python3-pip
sudo apt-get install libhdf5-serial-dev hdf5-tools libhdf5-dev zlib1g-dev zip libjpeg8-dev
sudo pip3 install -U pip
sudo pip3 install protobuf==3.3.0
sudo pip3 install -U numpy
sudo pip3 install -U grpcio absl-py py-cpuinfo psutil portpicker six mock requests gast astor termcolor protobuf keras-preprocessing wrapt google-pasta
sudo pip3 install -U h5py
sudo pip3 install -U keras-applications
sudo pip3 install -U future
sudo pip3 install -U scipy
sudo pip3 install -U setuptools testresources
pip3 list
```

Then check if we meet the requirement to install tensorflow-gpu=1.15.0. The current installed version should be at least as follows:
numpy==1.16.1, future==0.17.1, mock==3.0.5, h5py==2.9.0, gast==0.2.2, keras_preprocessing==1.0.5, keras_applications==1.0.8, scipy==1.4.1
If it satisfies the requirement, we can continue to install the tensorflow-gpu=1.15.0. 
Firstly, please find the corresponding tensorflow-gpu nvidia version on Nvidia website and download it.
Then simply follows these commands to install the remained environments:

```bash
sudo pip3 install -U (the wheel document of downloaded tensorflow-gpu)
sudo pip3 install -U python3-matplotlib
sudo pip3 install -U pillow
sudo apt-get install python3-keras
sudo pip3 install pycuda
```

Then we have all environments needed. In this process, some wheels might build for too long and fail. Please find online resources to build from raw in this case.

### Environment installation on linux or Windows ###
Firstly, please create conda environment with python version greater or equal to 3.6.6. Then you can follow these commands to install the requirements needed. 
```bash  
conda install pandas>=0.23.4
conda install keras>=2.2.4
conda install tensorflow-gpu>=1.11.0
conda install numpy>=1.15.2
conda install scipy>=1.1.0
conda install scikit-learn>=0.20.0
conda install scikit-image>=0.14.1
```
Then it should work fine.

## Training and Results

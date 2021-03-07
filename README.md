# CalWeeds: a large realistic weed dataset and multi-label classification between plants and weeds #
This repository makes available the source code and public dataset for our work, "Deep-CNN based Real-Time Robotic Multi-Class Weed Identification" submitted to Internation Conference on Intelligent Robots and Systems (IROS) 2021. 

Here, our first contribution is the first adequately large image dataset CalWeeds (one/multiple kinds of weeds in one image), a library of 7702 annotated images taken from 16 different locations including 11 most common weeds in fields and gardens in California and Central China. Second, we provide a thorough pipeline from training these models with maximum efficiency to deploying the TensorRT-optimized model onto a single board computer. Third, we employ our own autonomous mobile robot and demonstrate real-time weed detection. Based on CalWeeds dataset and the pipeline, we present a baseline for classification performance using the benchmark deep learning models: DenseNet121, InceptionV3, MobileNetV2, ResNet50, and Xception. Among them, MobileNetV2, with both the shortest inference time and lowest memory consumption, is the most competitive candidate for real-time applications.

## Download the dataset images and our trained models ##

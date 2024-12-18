# YOLOv5 on MNIST Dataset
Team members:
- 王一  ：Model training，github upload
- 王铁凝 ： Model evaluation
- 孙思瀚 ： Model evaluation

This repository demonstrates how to use [YOLOv5](https://github.com/ultralytics/yolov5) to perform object detection on the MNIST dataset. YOLOv5, a state-of-the-art object detection model, is adapted to identify handwritten digits (0-9) in images from the MNIST dataset.

## Table of Contents
- [Introduction](#introduction)

## Table of Contents
- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Training YOLOv5 on MNIST](#training-yolov5-on-mnist)
- [Evaluation](#evaluation)
- [Prerequisites](#Prerequisites)


## Introduction

The MNIST dataset is a collection of handwritten digits, commonly used for training image processing systems. While YOLOv5 is typically used for general object detection tasks, we adapt it here for digit classification by treating each digit as a distinct object.You can check our trained models and tested accuracy in our runs folder. For most types, we have reached 98% standard.The following pictures are our test results
![image](https://github.com/user-attachments/assets/079fb86b-d2e7-44f4-b437-02294f20a1b6)

## Getting Started
- First prepare a code software, here we use pycharm
- Configure the environment based on the dependencies in requirements.txt

## Training YOLOv5 on MNIST
The original MNIST dataset and its corresponding labels are placed in the datasets folder.  
The model file is in the model folder.

- Usage - Single-GPU training:
```
python train.py --data coco128.yaml --weights yolov5s.pt --img 640  # from pretrained (recommended)
python train.py --data coco128.yaml --weights '' --cfg yolov5s.yaml --img 640  # from scratch
```
- The command line used given the trained model is as follows
```
python train.py --data datasets/mnist/mnist.yaml --epochs 4 --weights models/yolov5m.pt --cfg models/yolov5m.yaml  --batch-size 16
```
## Evaluation
- You can use our trained model for evaluation or use your own model. Our model evaluation command is as follows：
```
python val.py --weights runs/train/exp/weights/best.pt --data datasets/mnist/mnist.yaml --img 640
```   


## Prerequisites
Before running this repository, make sure to install the following dependencies:
- Python 3.8 or higher
- [PyTorch](https://pytorch.org/)
- [YOLOv5 dependencies](https://github.com/ultralytics/yolov5#requirements)
- Other dependencies (e.g., numpy, pandas, matplotlib, etc.) can be installed via the `requirements.txt` file.

Clone the repository:
```bash
git clone https://github.com/Yikinge/YOLO-mnist-
cd YOLO-mnist-

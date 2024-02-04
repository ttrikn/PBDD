# PBDD
This is the open source code for paper: A Prompt-Based Learning Approach for Few-Shot Social Media Depression Detection
## Table of Contents
- [Paper Abstract](##PaperAbstract)
- [Preparation](##Preparation)
- [Running](##Running)
- [Training](##Training)
- ## Paper Abstract

- ## Preparation
### Data preprocessing
As mentioned in our paper, in order to train our model, you can download the Original Twitter dataset here: [[Twitter]](https://pan.baidu.com/s/1RI3l8fomIXHuR8e0_hUyhA?pwd=aea6). You can preprocess the dataset by the codes in the folder `datasets_pre_processing` following the steps in our paper, or you can get the proprecessed data from :[[Dataset]](https://pan.baidu.com/s/1eqYyXg6Y0PQkh-AHnpUD1g?pwd=b2lx) directly. You can also use other multimodal sentiment datasets by adjusting to the same structure as folder `datasets`.

### Environment

* Python 3.8
* PyTorch 1.8.1
* torchaudio 0.8.1
* torchvision 0.9.1
* transformers 4.6.0
* tqdm 4.65.0
* timm 0.4.12
* opencv-python 4.5.4.58
* numpy 1.24.3
* scipy 1.10.1

## Running
To get a quick start, you can download the pretrained unsupervised representation model from [[Pretrained Model]](https://pan.baidu.com/s/1hKf3CdJjHeh9KBeZv6OIrA?pwd=0dph) and put into folder `model`

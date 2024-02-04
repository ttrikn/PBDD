# PBDD
This is the open source code for paper: A Prompt-Based Learning Approach for Few-Shot Social Media Depression Detection
## Table of Contents
- [Paper Abstract](##PaperAbstract)
- [Preparation](##Preparation)
- [Running](##Running)
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
To get a quick start, you can download the pretrained unsupervised representation model from [[Pretrained Model]](https://pan.baidu.com/s/1hKf3CdJjHeh9KBeZv6OIrA?pwd=0dph) and put into folder `model`, then you should adjust the configuration in the `param.py` to meet your device requirements. After all the preparation work is completed, you can run the following command to start training.
```
python main.py
```
The prediction result will be saved in a .txt file in folder `output` , and the trained models ckpt will be saved in output/twitterdp+/[s1][d1][t1][ps111][nf_resnet50][lp11].

[s1], [d1] and [t1] stand for "train_few1.tsv" (the few-shot training file), "dev_few1.tsv" (the few-shot development file) and template 1 respectively.

[ps111] represents --prompt_shape is set to "111" here. This parameter shows the number of learnable tokens in each [LRN].We set --prompt_shape to "111" and each [LRN] will contain one learnable token when running. It only works and appears in the save path when we use learnable templates (template 1).

[nf_resnet50] suggests that we use NF-ResNet50 as the visual encoder (default setting) and [lp11] means we set the local pooling scale to 1×1 here.Of course you can try other values to acquire better performance.

# PBDD
This is the open source code for paper: A Prompt-Based Learning Approach for Few-Shot Social Media Depression Detection
## Table of Contents
- [Paper Abstract](##PaperAbstract)
- [Preparation](##Preparation)
- [Running](##Running)
- ## Paper Abstract

>The widespread use of social media has gradually unlocked the potential of utilizing its data for identifying depression. This paper introduces a Prompt-Based Depression Detection method (PBDD) for social media, aiming to effectively identify signs of depression in social media content. We designed a depression sentiment analysis model that leverages the concept of prompt learning.By deeply analyzing text and multimedia content on social media, the model effectively discerns depressive tendencies and related emotional characteristics. Considering the noisy nature of social media data and the complexity of multimodal features, the study incorporates a high-quality data sampling method to filter and optimize input data. This ensures the high quality of data during training and testing, significantly enhancing the model’s accuracy and reliability. Comprehensive experiments and analyses conducted on multiple authoritative datasets demonstrate that our method outperforms existing approaches in depression detection tasks, offering significant advantages.

<img src="https://github.com/ttrikn/PBDD/blob/main/script/arthitecture.png" width="1000"></img>

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
To get a quick start, you can download the pretrained unsupervised representation model from [[rot Model]](https://pan.baidu.com/s/1hKf3CdJjHeh9KBeZv6OIrA?pwd=0dph) and put into folder `model`, then you should adjust the configuration in the `param.py` to meet your device requirements. After all the preparation work is completed, you can run the following command to start training.
```
python main.py
```
The prediction result will be saved in a .txt file in folder `output` , and the trained models ckpt will be saved in output/twitterdp+/[s1][d1][t1][ps111][nf_resnet50][lp11].

[s1], [d1] and [t1] stand for "train_few1.tsv" (the few-shot training file), "dev_few1.tsv" (the few-shot development file) and template 1 respectively.

[ps111] represents --prompt_shape is set to "111" here. This parameter shows the number of learnable tokens in each [LRN].We set --prompt_shape to "111" and each [LRN] will contain one learnable token when running. It only works and appears in the save path when we use learnable templates (template 1).



[nf_resnet50] suggests that we use NF-ResNet50 as the visual encoder (default setting) and [lp11] means we set the local pooling scale to 1×1 here.Of course you can try other values to acquire better performance.

At the same time, we also provide an interface for testing a single sample. You can use the method `evaluate_on_demo` in `main.py` and find the pre-trained model from[[pre-trained model]](https://pan.baidu.com/s/1WRL3h5lvmadq_w_peiDvog?pwd=g83e). It should be noted that the data storage format needs to be consistent with the training stage.

## What's more

<img src="https://github.com/ttrikn/PBDD/blob/main/script/frontend.png" width="1000"></img>

We plan to implement an end-to-end system to simulate social media emotion recognition and depression detection in the near future. If you are interested in our work, please feel free to contact us:
   - Heyang Feng : 1245020424@qq.com
   - Xianxu Zhu : 1591694407@qq.com

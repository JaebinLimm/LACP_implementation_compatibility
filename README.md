

# LACP code execution issue about CUDA version

**I talk about [LACP](https://github.com/Pilhyeon/Learning-Action-Completeness-from-Points) (Learning Action Completeness from Points for Weakly-supervised Temporal Action Localization (ICCV 2021 Oral)) code implementation about different CUDA version.**


## Motivation
### Run LACP code on RTX3090
I had tried to run official LACP code on RTX3090, but faced a CUDA compatility issue.<br>
The issue is that RTX 3090 is only compatible with CUDA version 11 or higher.<br>
So I attempted to change pytorch and torchvision that support CUDA version 11 or higher.

## Prerequisites
Required environment's dependecies are as follows. <br>
**(A -> B: A is an officially recommended version, B is a changed version to support CUDA version 11.)**

### Dependencies
* python == 3.6 &#8594; **3.7**<br>
* cuda==10.2 &#8594; **>=11.0**<br>
* joblib==0.13.0<br>
* numpy==1.18.0<br>
* pandas==1.1.4<br>
* scikit-learn==0.20.0<br>
* scipy==1.4.1<br>
* tensorboard==1.15.0<br>
* tensorboard-logger==0.1.0<br>
* tensorflow==1.15.2<br>
* tensorflow-estimator==1.15.1<br>
* torch==1.6.0 &#8594; **1.7.1+cu110**<br>
* torchvision==0.7.0 &#8594; **0.8.2+cu110**<br>
* tqdm==4.31.1<br>

### Setup procedure
1. Crete an environment with python 3.6.<br>
2. Install following code on environment.<br>
~~~
pip install torch==1.7.1+cu110 torchvision==0.8.2+cu110 -f https://download.pytorch.org/whl/torch_stable.html
~~~
3. Install other libraries excepting pytorch and torchvision using [requirements.txt](https://github.com/Pilhyeon/Learning-Action-Completeness-from-Points/blob/main/requirements.txt) of offical LACP code.<br>
4. Finally, install `conda install protobuf==3.20.*`.<br>
---

## Reproduction 
## References
## Citation


**수정중...**



# LACP code implementation issue about CUDA version

I discuss about 'Learning Action Completeness from Points ([LACP](https://github.com/Pilhyeon/Learning-Action-Completeness-from-Points)) for Weakly-supervised Temporal Action Localization (ICCV 2021 Oral)' code implementation about different CUDA version.


## Motivation
### CUDA version conflict on RTX 3090
I had tried to run official LACP code on RTX3090, but faced a CUDA compatility issue.<br>
The issue is that RTX 3090 is only compatible with CUDA version 11 or higher.<br>
So I attempted to change pytorch and torchvision that support CUDA version 11 or higher.

## Prerequisites
Required the environment's dependecies are as below. <br>
(A -> B: A is an officially recommended version, B is a changed version to support CUDA version 11.)

### Dependencies
* python == 3.6
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
1. Create the environment with python 3.6.<br>
2. Install pytorch and torchvision on the environment by writing following code.<br>
~~~
pip install torch==1.7.1+cu110 torchvision==0.8.2+cu110 -f https://download.pytorch.org/whl/torch_stable.html
~~~
3. In additional, set up other libraries excepting pytorch and torchvision using [requirements.txt](https://github.com/Pilhyeon/Learning-Action-Completeness-from-Points/blob/main/requirements.txt) of offical LACP code<br>
---

## Reproduction results
||GTX 1080TI|RTX TITAN|RTX 3090_a|RTX 3090_b|A6000_a|A6000_b|
|----------------|----------------|----------------|----------------|----------------|----------------|----------------|
|Test_acc|0.7571|0.7429|0.7238|0.7238|0.7238|0.7238|
|average_mAP[0.1:0.7]|0.5252|0.5277|0.5257|0.5257|0.5235|0.5235|
|average_mAP[0.1:0.5]|0.6285|0.6270|0.6262|0.6262|0.6229|0.6229|
|average_mAP[0.3:0.7]|0.4399|0.4443|0.4434|0.4434|0.4410|0.4410|
|mAP@0.1|0.7610|0.7586|0.7549|0.7549|0.7527|0.7527|
|mAP@0.2|0.7158|0.7137|0.7081|0.7081|0.7069|0.7069|
|mAP@0.3|0.6561|0.6484|0.6474|0.6474|0.6440|0.6440|
|mAP@0.4|0.5653|0.5647|0.5664|0.5664|0.5622|0.5622|
|mAP@0.5|0.4442|0.4494|0.4540|0.4540|0.4487|0.4487|
|mAP@0.6|0.3373|0.3443|0.3442|0.3442|0.3464|0.3464|
|mAP@0.7|0.1964|0.2147|0.2049|0.2049|0.2037|0.2037|
## References
https://docs.nvidia.com/deploy/cuda-compatibility/index.html<br>
https://pytorch.org/get-started/previous-versions/<br>
https://velog.io/@somnode/gpu-cuda-driver-tensorflow-pytorch-version-compatibility<br>
## Citation

**수정중...**

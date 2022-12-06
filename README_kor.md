

# LACP code execution issue about CUDA version

**I talk about [LACP](https://github.com/Pilhyeon/Learning-Action-Completeness-from-Points) (Learning Action Completeness from Points for Weakly-supervised Temporal Action Localization (ICCV 2021 Oral)) code execution about different CUDA version.**


## Motivation
### Run LACP code on RTX3090
RTX 3090 요구하는 CUDA 버전과 LACP에서 권장되는 CUDA 버전이 다름.
따라서 이를 해결해주기 위해 CUDA version 11 이상을 지원하는 pytorch와 torchvision을 설치함.

## Prerequisites
요구되는 가상환경 디펜던시는 다음과 같음.<br>
**(A->B: A는 공식적으로 권장되는 버전이고, B는 CUDA 버전 11 이상에 호환되기 위해 바꾸어준 버전이다.)**

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
1. pytorch, torchvision 외의 다른 라이브러리를 동일하게 설치해주기 위해 python version은 3.7로 가상환경을 생성합니다.
2. 다음 코드를 이용하여 생성한 가상환경에 CUDA 11.0에 호환되는 pytorch와 torchvision를 설치합니다.
~~~
pip install torch==1.7.1+cu110 torchvision==0.8.2+cu110 -f https://download.pytorch.org/whl/torch_stable.html
~~~
3. LACP code의 [requirements.txt](https://github.com/Pilhyeon/Learning-Action-Completeness-from-Points/blob/main/requirements.txt)에서 pytorch와 torchvision을 제외한 나머지 라이브러리를 설치합니다.
4. 마지막으로 `conda install protobuf==3.20.*`를 설치합니다.	
---

## Reproduction 
1080ti, titan, RTX 3090-a, RTX 3090-b, A6000-a, A6000-b로 총 6개의 서버로 재현함.
## References
## Citation


**수정중...**
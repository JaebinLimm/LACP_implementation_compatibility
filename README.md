
# LACP code execution about cuda version

**I talk about LACP code execution about different cuda version.**

## Motivation
### Run LACP code on RTX3090
~~LACP code 실행 중 RTX3090에서는 CUDA 최소 지원 버전과 기존 LACP가 요구하는 pytorch 권장 버전이 달라 다른 pytorch 버전에서 오류 없이 잘 작동되는지 보고자 함<br>
기존 LACP는 CUDA 10.2와 Pytorch 1.6이 권장되지만 RTX3090부터는 CUDA 버전이 11.0 이상만 호환이 가능하여 이에 맞는 파이토치 버전을 깔아줘야 함.<br>
따라서, python, pytorch, torchvision version만 CUDA 11.0이상에 맞는 버전으로 맞추어 주고 나머지 라이브러리는 동일한 버전을 사용하여 최대한 기존 LACP 권장 환경에 맞게 해주어 실행하고자 함.<br>
최종적으로 다른 버전의 python, pytorch, torchvision을 설치하였을 때 LACP code에서 동일한 결과를 보이는지를 알아보고자 함.~~

RTX 3090 서버에서 지원하는 cuda 버전과 LACP에서 요구되는 cuda 버전이 호환되지 않음.
따라서 이를 해결해주기 위해 그래픽 카드에 맞는 cuda 버전 설치 후 그에 맞는 파이썬, 파이토치, 토치비전 등을 고려하여 맞추어 주는 실험을 진행

## Prerequisites
요구되는 가상환경 디펜던시는 다음과 같음.<br>
**A->B는 호환을 위해 바꾸어준 버전**

### Dependencies
* **python == 3.6 &#8594; 3.7**<br>
* **cuda==10.2 &#8594; >=11.0**<br>
* joblib==0.13.0<br>
* numpy==1.18.0<br>
* pandas==1.1.4<br>
* scikit-learn==0.20.0<br>
* scipy==1.4.1<br>
* tensorboard==1.15.0<br>
* tensorboard-logger==0.1.0<br>
* tensorflow==1.15.2<br>
* tensorflow-estimator==1.15.1<br>
* **torch==1.6.0 &#8594; 1.7.1+cu110**<br>
* **torchvision==0.7.0 &#8594; 0.8.2+cu110**<br>
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

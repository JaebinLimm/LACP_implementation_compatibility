# LACP code implementation in RTX3090
## Version compatibility check in LACP code

본 레포지토리는 RTX3090 환경에서 LACP code가 동일한 결과가 나오는지에 대한 과정을 다룹니다.<br>
LACP code 실행을 위해 서버를 돌리던 중 기존 titan 서버에서 RTX3090으로 코드를 옮겨 실행하고자 하였으나, RTX3090부터는 CUDA 버전이 11.0 이상만 호환이 가능하여 이에 맞는 파이토치 버전을 깔아 줄 필요가 있었습니다.   
따라서, python, pytorch, torchvision version만 CUDA 11.0이상에 맞는 버전으로 맞추어 주고 나머지 라이브러리는 동일한 버전을 사용하여 최대한 기존 LACP 권장 환경에 맞게 해주어 실행하였습니다.<br>
최종적으로 다른 버전의 python, pytorch, torchvision을 설치하였을 때 LACP code에서 동일한 결과를 보이는지를 알아보고자 합니다.


## Recommended Environment
**python == 3.6 &#8594; 3.7**<br>
**cuda==10.2 &#8594; >=11.0**<br>
joblib==0.13.0<br>
numpy==1.18.0<br>
pandas==1.1.4<br>
scikit-learn==0.20.0<br>
scipy==1.4.1<br>
tensorboard==1.15.0<br>
tensorboard-logger==0.1.0<br>
tensorflow==1.15.2<br>
tensorflow-estimator==1.15.1<br>
**torch==1.6.0 &#8594; 1.7.1+cu110**<br>
**torchvision==0.7.0 &#8594; 0.8.2+cu110**<br>
tqdm==4.31.1<br>


**수정중...**

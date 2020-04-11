
## 1. Loss Surface 란?

신경망을 훈련시킨다는 것은 고차원의 손실 함수에서 파라미터를 업데이트해가며 전역 최저점을 찾아가는 과정입니다.
신경망의 훈련은 신경망의 구조, 최적화 방법 그리고, 가중치 초기화 등 다양한 변수의 영향을 받습니다.
즉, 네트워크를 어떻게 설정하느냐에 따라 신경망의 훈련은 쉬울수도, 어려울 수도 있습니다. 
<img src="./img/intro1.PNG"></img>

신경망 함수는 고차원 함수이기때문에, 네트워크가 어떻게 학습이 되고 있는지 알기 어렵습니다.
하지만, 고차원의 로스 함수를 사람이 이해할 수 있는 3차원 공간안에 표현함으로써, 신경망의 훈련 과정을 더 잘 이해할 수 있으며, 인사이트를 얻을 수 있습니다.  

### Loss Surface 만드는 법  
Loss Surface를 시각화하는 방법은 두개의 가우시안 분포를 따르는 랜덤 방향 벡터를 만드는 것입니다. (0,0) 의 중앙 지점은 이미 훈련된 파라미터에서의 Loss 값으로 최저점을 의미한다고 볼 수 있습니다. 
두개의 방향 벡터를 만든 뒤, 각 방향벡터에 -1 부터 1까지의 상수를 곱하고, 기존 네트워크의 학습된 파라미터와 함하여 Loss Surface 를 시각화 합니다.  
<img src="./img/intro2.PNG"></img>

위 방법을 사용함으로써, 고차원의 Loss Surface를 3차원 좌표에 표현을 할 수 있습니다. 
Loss Surface에 관한 자세한 설명 및 논문 리뷰는 <a href="https://youtu.be/sAslF_B-JBE">링크</a>를 참조바랍니다. 

## 2. Loss Surface 가 강화학습을 만날 때,
Loss Surface는 고차원의 변수를 학습하는 딥러닝 모델 어느곳에서도 사용할 수 있습니다. 다음은 mnist 데이터를 신경망에 훈련시킨 Loss Surface 입니다.

<img src="./img/mnist_loss_surface.png"></img>

이번 프로젝트에서는 강화학습 중에서도 신경망을 사용한 Q Network 에서 학습이 잘 안되고, DQN 이 Q Network가 가지는 여러 한계점들을 극복하면서 좋은 성능을 낼 수 있었는지를 Loss Surface를 통해서 확인해보도록 하겠습니다. 

### 1. Q-Network Loss Surface 

Q-Learning 의 수렴은 이루어지지 않음. Q-table 은 증명이 되어 있음. 하지만 Q-Network 에서는 학습이 되지 않는데 그 이유는 다음 두가지 이유가 있음. 
-Correlation with sample data
-Non stationary 

<img src="./img/q_learning_loss_surface.png"></img>

### 2. DQN Loss Surface 
-Deep , Replay, Separated Network

<img src="./img/dqn_loss_surface.png"></img>



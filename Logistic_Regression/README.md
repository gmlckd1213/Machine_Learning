# Logistic_Regression

선형회귀에서 확률이 음과 양의 방향으로 무한대로 뻗어나가는것 

<img width="188" alt="image" src="https://user-images.githubusercontent.com/63540952/157892755-0d43cbcc-c94b-40df-8576-4f7a049baf94.png">

- 확률 값 p는 선형 판별식 값이 커지면 1, 작아지면 0에 가까운 값이 됨
- 무한대 범위를 갖는 선형 판별식 결과로 (0,1) 범위의 확률 값을 얻게 됨
- 확률 값 0.5를 기준으로 이진 분류를 수행할 수 있게 됨
- *시그모이드(sigmoide)*함수라고도 부른다
- 다중일때 softmax!!!!
<img width="372" alt="image" src="https://user-images.githubusercontent.com/63540952/157893593-e1f95aa4-c2d4-4362-a001-4a349e649c49.png">

x 데이터가 주어졌을 때 확률을 예측하는 로지스틱 회귀 분석은 학습 데이터를 잘 설명하는 로지스틱 함수의 a와 b를 찾는 문제

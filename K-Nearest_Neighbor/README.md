# K-Nearest Neighbor

- K-Nearest Neighbor : k 최근접 이웃
- 회귀와 분류에 사용되는 매우 간단한 지도학습 알고리즘
- 다른 알고리즘에 비해 쉽지만, 연산속도가 느림
- KNN 모델 성능을 높이기 위해서는 **정규화(Normalization)** 작업을 진행해야 함
- 모든 데이터가 같은 범위의 데이터를 가질 때 좋은 성능을 보임

<br>

회귀 : k개 값의 평균을 계산하여 값을 예측<br>
분류 : 가장 많이 포함된 유형으로 분류

## k값의 중요성
- k(탐색하는 이웃 개수)에 따라 데이터를 다르게 예측할 수도 있음
- k값에 따라 예측 값이 달라지므로 적절한 k 값을 찾는 것이 중요(기본 5)
- 일반적으로
    * k를 1로 설정 안함 -> 이웃 하나로 현재 데이터를 판단하기에는 너무 편향된 정보
    * k를 홀수로 성정 -> 짝수인 경우 과반수 이상의 이웃이 나오지 않을 수 있음
- 검증 데이터로 가장 정확도 높은 k를 찾아 knn알고리즘의 k로 사용


## 거리 구하기

### 유클리드거리(Euclidean Distance)
<img width="398" alt="스크린샷 2022-03-10 오전 12 44 42" src="https://user-images.githubusercontent.com/63540952/157476687-ed9928d5-6a2a-4f13-8856-97c4086bbf3b.png">

### 맨하튼 거리(Manhattan Distance)
<img width="389" alt="스크린샷 2022-03-10 오전 12 45 36" src="https://user-images.githubusercontent.com/63540952/157476890-37eff97e-b214-4678-993f-042053841eec.png">

## 장점
- 수학적 거리를 계산하는 방법만 이해하면 되니 비교적 다른 알고리즘에 비해 쉬움
- 거리, 횟수, 점수와 같은 숫자로 구분된 속성에 우수한 성능 보임
- 예측 시점에 기존 데이터와의 거리를 계산하므로 별도의 모델 학습이 필요x
- 학습은 단지 기존 데이터를 저장하는 과정일 뿐
- 모델을 별도로 구축하지 않아 *Lazy Model*이라고 부름

## 단점
- 데이터 하나를 예측할 때마다 전체 데이터와의 거리를 계산하니 예측 속도가 느림
- 오직 가까운 이웃을 통해 예측하므로 예측 값이 지역 정보에 많이 편향될 수 있음
- k 개수가 적거나 예외적인 데이터가 이웃으로 존재 시 예측 값 틀릴 가능성 높음
- 결과를 설명하기가 어렵다(시각화 어려움)

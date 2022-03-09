# Machine_Learning

- 지도학습 : 학습 대상이 되는 데이터에 정답을 주어 규칙성, 즉 데이터의 패턴을 배우게 하는 학습 방법
- 비지도 학습 : 정답이 없는 데이터 만으로 배우게 하는 학습 방법
- 강화 학습 : 선택한 결과에 대해 보상을 받아 행동을 개선하면서 배우게 하는 학습 방법


## 지도학습 (분류, 회귀)

- 회귀는 연속적인 숫자를 예측하는 것
- 연속적인 숫자는 두 값 사이의 중간 값이 충분히 존재 할 수 있는 숫자를 의미
- 출력 값에 연속성이 있는지 확인하면 분류와 회귀 문제를 쉬게 구분 가능


|회귀 문제|분류 문제|
|-|-|
|LinearRegression|DecisionTreeClassifier|
|KNeighborsRegressor|KNeighborClassifier|
|DecisionTreeRegressor|LogisticRegression|
|SVR|SVC|
|RandomForestRegressor|RandomForestClassifier|
|||
|mean_absolute_error|accuracy_score|
|mean_squared_error|recall_score|
|root mean_squared_error|precision_score|
|mean_absolute_percentage_error|classification_report|
|r2_score|confusion_matrix|


행(row)
- 개체(Instance)
- 관측치(Observed Value)
- 기록(Record)
- 사례(Example)
- 경우(Case)

열(Column)
- 특성(Feature)
- 속성(Attribue)
- 변수(Variable)
- 필드(Field)

* 독립변수 : 예측을 위해 모델이 사용하는 속성(입력변수)
* 종속변수 : 모델이 예측하고자 하는 목표 값(출력변수)


#### 데이터 분리

- 데이터 셋을 학습용, 검증용, 평가용 데이터로 분리
- 실전: 학습용(Training) + 검증용(Validation) + 평가용(Testing)
- 학습: 학습용(Training) + 평가용(Testing)


#### 과대적합(Overfitting)
- 학습 데이터에서 점수가 매우 높았는데, 평가 데이터에서 점수가 매우 낮은 경우
- 학습 데이터에 대해서만 잘 맞는 모델 -> 실전에서 예측 성능이 좋지 않음

#### 과소적합(Underfitting)
- 학습 데이터보다 평가 데이터 점수가 더 높거나 두 점수 모두 너무 낮은 경우
- 모델이 너무 단순하여 학습 데이터에 적절히 훈련되지 않은 경우

## Scikit-Learn
- 지도/비지도 학습 알고리즘을 제공하는 대표적인 파이썬 라이브러리
- 오픈소스로서, 무료로 사용가능
- 토이 데이터셋을 포함하고 있어 학습에 용이

### 순서
1. 환경준비 : 기본 라이브러리와 대상 데이터를 가져와 이후 과정을 준비
2. 데이터 이해 : 분석할 데이터를 충분히 이해할 수 있도록 다양한 탐색 과정을 수행
3. 데이터 준비 : 전처리 과정을 통해 머신러닝 알고리즘에 사용할 수 있는 형태의 데이터를 준비
4. 모델링 : 회귀 문제인지 분류 문제인지 명확히 구분

### *모델링 코드 순서*

1. 불러오기 : 사용할 라이브러리 import
2. 선언하기 : 사용할 알고리즘을 모델로 선언
3. 학습하기 : 모델.fit(x_train, y_train) 형태로 학습
4. 예측하기 : 모델.predict(x_test) 형태로 예측 값 만들기
5. 평가하기 : 예측 값과 실제 값으로 평가 평가지표(y_test, y_pred)

## 성능평가

- 분류 모델 평가  (정확도를 높이기)
  * 0인지 1인지를 예측
  * 실제 값도 0과 1이고 예측 값도 0 과 1임
  * 0을 1ㅇ로 1을 0으로 예측가능
  * 예측 값이 실제 값과 많이 같을 수록 좋은 모델
  * 정확히 예측한 비율로 모델 성능을 평가


- 회귀 모델 평가   (오차를 줄이기)
  * 회귀 모델이 정확한 값을 예측하기는 어려움
  * 예측 값과 실제 값에 차이(오차)가 존재
  * 예측 값이 실제 값에 가까울 수록 좋은 모델
  * 예측한 값과 실제 값의 차이(오차)로 모델 성능평가

<img width="725" alt="스크린샷 2022-03-09 오후 7 47 32" src="https://user-images.githubusercontent.com/63540952/157426812-d338dcb8-4dbd-492d-ab16-84d928523fca.png">



<img width="710" alt="스크린샷 2022-03-09 오후 7 56 48" src="https://user-images.githubusercontent.com/63540952/157428232-3cf266b7-c33b-4cb9-8e83-a7386b9e2415.png">

- SST(Sum Sqaured Total(전체오차)) : 최소한 평균보다는 성능이 좋아야 하니, 우리에게 허용된 오차
- SSR(Sum Squared Regression) : 전체 오차 중에서 회귀식이 잡아낸 오차
- SSE(Sum Squared Error) : 전체 오차 중에서 회귀식이 여전히 잡아내지 못한 오차

#### 결정계수(R-Squared)

- 얼마나 잘했는가?
- 전체 오차 중에서 회귀식이 잡아낸 오차 비율(일반적으로 0~1사이)
- r제곱이 1이면 MSE=0 모델이 데이터를 완벽하게 학습한 것 
- 클수록 좋음!


## 회귀 정리
- MSE, RMSE, MAE, MAPE는 오류이므로 작을 수록 좋음
- R2 Score는 클 수록 좋음
- 단순히 오차 절대값, 오차 제곱으로 계산되는 MAE, MSE는 함수 사용시 실제값, 예측값 위치가 바뀌어도 되지만 -> 비추
- MAPE, R2 Score는 실제값 예측값 순서가 바뀌면 안됌.

## 혼동 행렬
- Confusion Matrix(오분류표)

<img width="382" alt="스크린샷 2022-03-09 오후 8 48 26" src="https://user-images.githubusercontent.com/63540952/157436149-9ef60931-618c-4abd-bf98-dac196ad67ea.png">

- TN(True Negative, 진음성) : 음성으로 잘 예측한 것 (음성->음성)
- FP(False Positive, 위양성) : 양성으로 잘 못 예측한 것(음성->양성)
- FN(False Negative, 위음성) : 음성으로 잘 못 예측한 것(양성->음성)
- TP(True Positive, 진양성) : 양성으로 잘 예측한 것(양성->양성)

### 정확도(Accuracy)
- 정분류율이라고 부르기도 함
- 전체 중에서 TN + TP 비율
- 가장 직관적으로 모델 성능을 확인할수 있는 평가 지표
<img width="342" alt="스크린샷 2022-03-09 오후 9 02 25" src="https://user-images.githubusercontent.com/63540952/157438279-ae9fad96-95ca-4f2e-978b-f6cc4fad3804.png">

### 정밀도(Precision)
- Positive로 예측한 것 중 실제 Positive 비율
- ex) 암이라 예측한 환자 중에서 실제 암 환자 비율
- 정밀도가 낮으면?
  - 암이 아닌데 암이라 했으니 불필요한 치료발생
<img width="228" alt="스크린샷 2022-03-09 오후 9 04 23" src="https://user-images.githubusercontent.com/63540952/157438589-d62a4c80-5fff-483b-a729-271c8f8295fe.png">

### 민감도(Recall)
- 실제 Positive 중에서 Positive로 예측한 비율
- 민감도(Sensitity)라고 부르는 경우가 많음
- ex) 실제 암인 환자 중에서 암이라고 예측한 환자의 비율
- 재현율이 낮으면?
  - 암인 사람에게 암이아니라 했으니 심각한 결과 초래

<img width="204" alt="스크린샷 2022-03-09 오후 9 16 25" src="https://user-images.githubusercontent.com/63540952/157440361-6461f9eb-d5bd-421d-8e1a-c27775cbfdb5.png">

### 특이도(Specificity)
- 실제 Negative 중에서 Negative로 예측한 비율
- ex) 실제 암이 아닌 환자 중에서 암이 아니라고 예측한 경우
- 특이도가 낮으면?
  - 암이 아닌데 암이라 했으니 불필요한 치료 발생

<img width="250" alt="스크린샷 2022-03-09 오후 9 19 18" src="https://user-images.githubusercontent.com/63540952/157440712-a5eae095-377b-448d-9154-74f1015ceb93.png">

### F1-Score
- 정밀도와 재현율의 조화평균
- 분자가 같지만 부모가 다를 경우 조화평균이 정확
- 정밀도와 재현율이 적적할게 요규 될 떄 사용

<img width="646" alt="스크린샷 2022-03-09 오후 9 25 04" src="https://user-images.githubusercontent.com/63540952/157441479-af8a3933-485e-4427-8106-8528ef2fd008.png">


*회귀 모델은 MAE, R2_score*<br>
*분류 모델은 confusion_matrix, classification_report*

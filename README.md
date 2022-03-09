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

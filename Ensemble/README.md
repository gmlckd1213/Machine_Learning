# Ensemble(앙상블)
- 보팅(Voting)
- 배깅(Bagging)
- 부스팅(Boosting)
- 스태킹(Stacking)


## 보팅(Voting)
- 여러 개의 분류기가 투표를 통해 최종 예측 결과를 결정하는 방식
- 다른 유형의 알고리즘 기반 분류기 사용
- 하드 보팅(Hard Voting)
    - 다수 분류기가 예측한 값이 최종 결괏값
    - 분류
- 소프트 보팅(Soft Voting)
    - 모든 분류기가 예측한 레이블 값의 결정 확률 평균을 구한 뒤 가장 확률이 높은 레이블 값을 최종 결과로 선정
    - 평균

<img width="366" alt="image" src="https://user-images.githubusercontent.com/63540952/158159836-71bc1430-6e13-4efb-abad-73d855a87b8f.png">


<img width="785" alt="image" src="https://user-images.githubusercontent.com/63540952/158159883-cc0ab7be-444e-4adc-a05a-f3578d57b8c4.png">

## 배깅(bagging)
- Bootstrap Aggregation의 약자
- 데이터로부터 부트스트랩 한 데이터로 모델을 학습시킨 후, 학습된 모델의 결과를 집계하여 최종 결과를 얻는 방법
- 같은 유ㅠ형의 알고리즘 기반 분류기 사용
- 데이터 분할 시 중복을 허용(복원 랜덤 샘플링 방식)
- 범주형 데이터는 투표방식으로 결과를 집계
- 연속형 데이터는 평균으로 결과를 집계

<img width="512" alt="image" src="https://user-images.githubusercontent.com/63540952/158160329-f2efc62e-e8bf-405d-8b14-1d3f09f432c7.png">

## 부스팅(Boosting)
- 같은 유형의 알고리즘 기반 분류기 여러 개에 대해 순차적으로 학습 수행
- 이전 분류기 예측이 틀린 데이터에 대해 올바르게 예측할 수 있도록 다음 분류기에게 가중치를 부여하면서 학습과 예측을 진행
- 계속하여 분류기에게 가중치를 부스팅하며 학습을 진행해 부스팅 방식이라 함
- 예측 성능이 뛰어나 앙상블 학습을 주도함
- 배깅에 비해 성능이 좋지만, 속도가 느리고 과적합 발생 가능성이 있음 -> 상황에 맞게 적절히 사용
- 배깅은 분류기들이 학습 시 상호 영향을 주지않고 학습이 끝난 후 그 결과를 종합하는 방법이며, 수브팅은 이전 분류기 학습 결과를 토대로 다음 분류기 학습 데이터 샘플 가중치를 조정해 학습을 진행하는 방법
- 대표적인 부스팅방법 : XGBoost, LightGBM
<img width="687" alt="image" src="https://user-images.githubusercontent.com/63540952/158165473-dff45fe6-2647-4031-8f38-523ea5ab16db.png">

## 스태킹(Stacking)
- 여러 모델의 예측 값을 최종 모델의 학습 데이터로 사용하여 예측하는 방법
- 현실 모델에서 많이 사용되지 않음
- 캐글 같은 미세한 성능차이로 승부를 결정하는 대회에서 사용됨
- 기본 모델로 4개 이상 선택해야 좋은 결과를 기대할 수 있음

<img width="803" alt="image" src="https://user-images.githubusercontent.com/63540952/158165256-eec10fe9-7e64-490d-b221-66954734945e.png">


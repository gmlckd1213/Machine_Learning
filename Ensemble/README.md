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



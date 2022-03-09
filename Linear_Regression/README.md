# Linear Regression

## 회귀
### **y = ax + b**
a = 기울기<br>
b = 절편

- 데이터는 다양한 형태를 가질 것이며 최선의 직선을 긋기가 어려움
- 최선의 기울기 a와 절편 b를 결정하는 방법이 필요
- 이것이 선형 회귀분석이며, 직선을 *회귀선*이라고 부름

최선의 회귀선을 찾자!
<br>

<img width="742" alt="스크린샷 2022-03-09 오후 10 57 36" src="https://user-images.githubusercontent.com/63540952/157456032-c1a58def-a53d-4aed-9057-c6fc30a7cc48.png">

## 단순 회귀
- 독립변수 개수로 회귀분석을 단순 회귀와 다중 회귀로 분류
- x값이 하나
- 단순회귀(Simple Regression)
    * 독립변수와 종속변수의 일대일 대응 관계성을 찾는 알고리즘
    * 반복 학습을 통해서 최선의 가중치와 편향을 찾음



## 다중 회귀(Multiple Regression)
- 여러 독립변수가 종속변수에 영향을 미칠 때 사용
- x값이 여러개

모델 학습 후 회귀 계수 확인
```

print(model.coef_)
print(model.intercept_)
#다중일때 회귀계수 확인
print(list(x_train[featured])
```

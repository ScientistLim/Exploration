# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 임정훈
- 리뷰어 : 김수진


# PRT(Peer Review Template)
- [ ]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
        - 해당 조건을 만족하는 코드를 캡쳐해 근거로 첨부
        
---

import matplotlib.pyplot as plt

# hour와 count의 관계 시각화
plt.figure(figsize=(12, 6))

plt.scatter(X_test['hour'], y_test, label='True', alpha=0.7)
plt.scatter(X_test['hour'], y_pred, label='Predicted', alpha=0.7)
plt.title('rent for hour')
plt.xlabel('hour')
plt.ylabel('rent')
plt.legend()

plt.show()

---

- [ ]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
        
---

from sklearn.linear_model import LinearRegression

# LinearRegression 모델 객체 생성
lr_model = LinearRegression()

# 모델 학습
lr_model.fit(X_train, y_train)

# 학습된 모델의 계수(coefficient) 및 절편(intercept) 확인
print("Coefficients:", lr_model.coef_)
print("Intercept:", lr_model.intercept_)

---
        
- [ ]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.

---

from sklearn.model_selection import train_test_split

# 사용할 feature 컬럼 선택 (예시: 'year', 'month', 'day', 'hour' 선택)
selected_features = ['year', 'month', 'day', 'hour']  # 실제로는 다양한 feature 조합을 시도해 볼 수 있습니다.

# X, y 데이터 정의
X = train[selected_features]
y = train['count']

# train/test 데이터 분리
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# 결과 확인
print(X_train.head())
print(y_train.head())

---
        
- [ ]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.

---
        
- [ ]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 하드코딩을 하지않고 함수화, 모듈화가 가능한 부분은 함수를 만들거나 클래스로 짰는지
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화했는지
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.

from sklearn.model_selection import train_test_split

x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.33, random_state=42)

(x_train.shape, y_train.shape), (x_test.shape, y_test.shape)

---


# 참고 링크 및 코드 개선
```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```

-----

Code Peer Review

# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 임정훈
- 리뷰어 : 김청빈

# PRT(Peer Review Template)
- [O]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
        - 해당 조건을 만족하는 코드를 캡쳐해 근거로 첨부
- **채점 근거**
      - 프로젝트1의 MSE 값이 잘 나왔음
          - mse:  2832.576603656798
      - 프로젝트2의 RMSE 값이 150 보다 조금 높음
          - rmse: 156.51050713451144
      - 시각화 표현을 잘하고 있음
          1. 프로젝트 1
              - 정답 데이터와 예측 데이터를 scatter plot으로 잘 시각화 하였다.
          2. 프로젝트 2
              - subplot을 사용하여 막대 그래프를 잘 시각화 하였다.
              - 정답 데이터와 예측 데이터를 scatter plot으로 잘 시각화 하였다.
              - ![image](https://github.com/kimCheongBin/Exploration/assets/48667883/cadd7900-17fd-44c2-9f18-2f96d8693bfd)
              - ![image](https://github.com/kimCheongBin/Exploration/assets/48667883/754f752b-b06f-463a-923d-bae78bf3f78d)


- [O]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
- **채점 근거** 
    1. 프로젝트 2
       - 데이터 정의부터 모델 학습까지 주석으로 모두 안내하고 있다.
       - 각 평가지표에 대한 안내가 잘 되어지고 있다.
       - ![image](https://github.com/kimCheongBin/Exploration/assets/48667883/085bd31f-bb46-43c4-81a0-b209c5a94dd6)


- [ ]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” ”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    실험이 기록되어 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.

- [ ]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.

- [O]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 하드코딩을 하지않고 함수화, 모듈화가 가능한 부분은 함수를 만들거나 클래스로 짰는지
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화했는지
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
- **채점 근거** 
  - 불필요한 할당이나 중복 없이 잘 작성됨
  - 경사하강법 구현의 경우, append를 사용하여 리스트에 추가하거나 return 으로 print를 주어 파이써닉하게 잘 작성함
    - ![image](https://github.com/kimCheongBin/Exploration/assets/48667883/5ffda9e2-8417-4204-9656-5b90a7b86332)



# Gradient Descent(매운맛)

## 목표

- [x] 2강에서 배운 선형회귀 분석과 비교하여 선형 모델 이외 적용 가능한 경사하강법- 선형회귀분석을 설명 => 경사하강법 알고리즘 수식을 정확히 이해하기
- [x] 경사하강법의 한계와 극복 방법(확률적 경사하강법) 알기 => 딥러닝에 널리 활용되는 방법
- [x] d-차원 벡터에 대한 그레디언트 벡터를 구하는 계산 해보기 => n제곱 다항식의 미분에 대한 공식 이용



### 경사하강법으로 선형회귀 계수 구하기

- ||y - XB||2 이고 **이를 최소화 하는 B**를 찾아야 함 
- n제곱 다항식의 미분에 대한 공식 이용

![image-20210805140313012](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805140313012.png)

<img src="C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805121244587.png" alt="image-20210805121244587" style="zoom:150%;" />

![image-20210805140536675](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805140536675.png)



- 목적식을 최소화하는 B를 구하는 경사하강법 알고리즘은 다음과 같다 (λ : 학습률)

![image-20210805140955859](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805140955859.png)

- 마이너스 + 마이너스 => 플러스 됨을 주의

![image-20210805141308279](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805141308279.png)

- 참고 - 노름에 제곱을 하게 된다면 식이 좀 더 간단해 진다

![image-20210805141754406](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805141754406.png)



### 경사하강법 기반 선형회귀 알고리즘

```python
# Input : X, y, lr, T, Output : beta

# norm: L2-노름을 계산하는 함수
# lr: 학습률
# T: 학습횟수
for t in range(T): # 보통 종료조건을 학습 횟수로 컨트롤 하는 경우가 많다
    error = y - X @ beta
    grad = - transpose(X) @ error
    beta = beta - lr * grad
```

- 학습률과 학습횟수를 적절하게 선택하는 것이 중요하다.



### 경사하강법은 만능?

- 미분가능하고 볼록한 함수에서 **적절한 학습률, 학습횟수**를 선택했을 때 수렴이 보장 (까다롭다)
- ||y - XB||2 은 회귀 계수 B에 대해 볼록함수이기에 충분히 돌리면 수렴
- 비선형회귀의 문제는 볼록하지 않을 경우가 있을 수 있기에 수렴이 항상 보장되지 않는다



### 확률적 경사하강법(stochastic gradient descent)

- 모든데이터(x) 데이터 한개 또는 일부(o)를 이용하여 업데이트
- 볼록이 아닌 목적식은 SGD를 통해 최적화
- 데이터의 일부를 사용하므로 연산자원을 좀 더 효율적으로 활용하는데 도움

![image-20210805142942706](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805142942706.png)

![image-20210805143114268](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805143114268.png)



### 확률적 경사하강법의 원리

- 전체데이터 (X, y), 목적식 L

![image-20210805143312098](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805143312098.png)



- SDG는 미니배치를 가지고 그레디언트 벡터를 계산
- 미니배치가 확률적으로 선택 => 목적식 모양이 바뀐다

![image-20210805143413673](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805143413673.png)

![image-20210805143438672](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805143438672.png)



- GD와 SGD의 직관적인 이해

![image-20210805143554236](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805143554236.png)

- mini batch size를 너무 작게 설정하면 SGD가 GD보다 느리게 수렴할 수도 있다

<img src="C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805143606239.png" alt="image-20210805143606239" style="zoom:200%;" />



### 확률적 경사하강법의 원리  -  하드웨어

![image-20210805143933428](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805143933428.png)

![image-20210805143946317](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805143946317.png)

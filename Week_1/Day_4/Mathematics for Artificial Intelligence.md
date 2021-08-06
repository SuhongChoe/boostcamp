# 딥러닝 학습방법 이해하기

## 목표

- [ ] 딥러닝의 원리에 대한 이해하기 (softmax, 활성함수, 역전파 알고리즘)
- [ ] 분류 문제에서 softmax 함수가 사용되는 이유
- [ ] softmax 함수의 결과값을 분류 모델의 학습에 어떤 식으로 사용되는지 알기



## 신경망(비선형 모델)

- X : 데이터를 모은 행렬, W : X의 행렬을 다른 차원으로 보내는 행렬

![image-20210805145137629](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805145137629.png)



- 출력 벡터의 차원 d => p 로 이동 (직관적 이해)

![image-20210805150035897](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805150035897.png)



- 주어진 문제가 어떠한 클래스에 해당하는지 => softmax 함수를 주로 이용

  ![image-20210805150700189](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805150700189.png)



- 출력 되는 부분을 확률로 해석할 수 있게 변환하는 연산
- 분류문제를 풀 때 (선형모델 + 소프트맥스) 함수 결합

![image-20210805150821865](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805150821865.png)

```python
def softmax(vec):
    denumerator = np.exp(vec - np.max(vec, axis=-1, keepdims=True))
    numerator = np.sum(denumerator, axis=-1, keepdims=True)
    val = denumerator / numerator
    return val
```



- 그러나 추론을 하는 경우엔 one-hot 벡터를 사용 => softmax 사용 x



## 신경망

- 선형모델 + 활성함수를 합성한 함수
- 활성함수는 벡터가 아닌 실수값을 받음
- 선형 모델을 통해 나온 결과물을 활성함수를 통해 비선형으로 만드는 네트워크 = > 뉴런 네트워크

![image-20210805152019831](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805152019831.png)



## 활성함수

- 비선형 함수로써 신경망을 비선형으로 만들어 주기 위한 매우 중요한 개념
- 활성함수를 쓰지 않으면 선형모델과 차이가 없다
- sigmoid, thanh, ReLU등이 있다. (현재 ReLU를 가장 많이 사용하고 있다)

![image-20210805152523823](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805152523823.png)



## 신경망을 수식으로 분해해보기

- 2 layer Network

![image-20210805152638725](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805152638725.png)



- 위의 과정을 반복하게 된다면 다층 퍼셉트론(MLP)이 만들어 진다.

![image-20210805152952312](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805152952312.png)

![image-20210805153033197](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805153033197.png)

![image-20210805153050282](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805153050282.png)



## 왜 층을 여러개를 쌓을까?

- 이론적으로는 2층 신경망으로 연속함수를 근사할 수 있다
- 층이 깊을을수록 목적함수를 근사하는데 필요한 뉴런의 숫자가 훨씬 빨리 줄어든다 => 좀 더 효율적인 학습 가능
- 그러나 층이 깊어질수록 최적화하는데 훨씬 더 많은 노력을 기울여야 한다.

![image-20210805153237839](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210805153237839.png)



## 역전파 알고리즘

 chain rule를 이용하여 맨 뒤 W(L) -> W(L-1)





## 궁금한 점

- [ ] 왜 softmax에서 exp를 사용할까?
- [ ] 왜 순전파는 중요하지 않음?
- [ ] latent 잠재벡터 => 활성화 함수를 통해 특징점을 추출할 수 있는 가능성이 있는 벡터라는 뜻
- [ ] 


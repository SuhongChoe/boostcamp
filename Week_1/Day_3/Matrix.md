# 행렬이 뭐예요?



## 행렬

- 벡터를 원소로 가지는 2차원 배열 (n x m, n by m행렬)
- numpy에서 행이 기본단위임을 명심하자!
- X = (xij)로 표시하기도 한다

![image-20210804102430758](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804102430758.png)



## 전치행렬

- 행과 열을 서로 바꿔 m x n 행렬이 된다.



## 행렬을 이해하는 방법

- 공간 상 여러 점들을 나타냄 (= 데이터들의 모임)
- 행렬의 행벡터 xi는 i번째 데이터
- 행렬의 xij는 i번째 데이터의 j번째 변수 값

![image-20210804103218345](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804103218345.png)



- 서로다른 두 데이터를 연결하는 함수 (멋진 말인듯)
- 행렬곱을 통해 벡터를 **다른 차원의 공간**으로 보내게 된다.
- 행렬곱을 통해 **패턴을 추출** 또는 **데이터 압축**을 할 수도 있다.

![image-20210804105624103](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804105624103.png)





## 행렬의 연산

##### 일반적인 연산

- 덧셈, 뺄셈, 성분곱, 스칼라
- 성분곱은 같은 위치의 원소끼리의 곱한 것

##### 행렬 곱셈

- i번째 행벡터와 j번째 열벡터 사이의 내적을 성분으로 가지는 행렬
- X의 행 개수와 Y의 열 개수가 같아야 한다
- numpy에서 @연산을 사용 X @ Y
- numpy.inner는 행끼리 계산(= Y의 전치행렬) 하는 것 이므로 혼동 주의!  (X 행의 개수 == Y행의 개수)

![image-20210804104659499](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804104659499.png)



## 역행렬

- 어떤 행렬 A의 연산을 거꾸로 되돌리는 행렬
  - 행과 열이 같고 detminant가 0이 아닌 경우에 계산 가능
- numpy.linalg.inv로 구할 수 있다.
- 만약 역행렬을 계산할 수 없다면 유사 역행렬(무어-펜로즈)을 이용
- numpy.linalg.pinv로 구할수 있음 

![image-20210804110951945](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804110951945.png)



## 응용

- 연립 방정식

![image-20210804114833288](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804114833288.png)



- 선형 회귀

- 데이터를 행렬 X로 표현

- y^(예측한것)과 y는 다름

- 직접 구할 때 y절편 항을 직접 추가해야 한다.

  (무어펜로즈 역행렬을 사용한 경우에는, y절편을 따로 추가해주지 않으면 x의 계수에 대해서만 추정을 해주기 때문)

![image-20210804115012691](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804115012691.png)

![image-20210804115145473](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804115145473.png)



## 궁금한점

- [x] 데이터와 변수의 차이점 - 차원의 개수에 해당하는것이 변수, 데이터는 말 그대로 주어진 데이터의 개수
- [x] 무어-펜로즈 역행렬 이용하여 직접 회귀분석을 할떄 y절편을 추가해야하는 이유 - y^=B1*x+B2*를 만들어 줘야하는데 추가하지 않으면 y^=B1*x 가 되기 때문임

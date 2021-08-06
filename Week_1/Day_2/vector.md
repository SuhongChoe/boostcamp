# **벡터**

- 공간에서 한 점을 나타냄
- 벡터는 원점으로부터 상대적 위치
- 벡터에 숫자(Scalar)를 곱해주면 길이만 변함

![image-20210803154800649](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210803154800649.png)



- 벡터는 숫자를 원소로 가지는 list 또는 array
- 벡터끼리 같은 모양을 가지면 연산 (+, -) 가능

![image-20210803155136407](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210803155136407.png)



- 같은 모양을 가지면 성분곱 가능

![image-20210803155229407](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210803155229407.png)



- 두 벡터의 덧셈은 다른벡터로부터 **상대적 위치이동**을 표현

![image-20210803155423773](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210803155423773.png)



## 벡터의 노름

- 원점에서부터의 거리
- L1 - 각 성분의 **변화량 절대값** 더한것
- L2 - 피타고라스 정리를 이용한 **유클리드 거리**

![image-20210803155739767](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210803155739767.png)



- 노름 종류에 따라 **기하학적 성질**이 다르다
- 머신러닝에선 각 성질들이 필요에 따라 사용됨으로 둘 다 아는것이 중요

![image-20210803160354103](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210803160354103.png)



- L1, L2 노름을 이용하여 두 벡터 사이의 거리 계산
- 벡터의 뺄셈을 이용
- 거꾸로 해도 같음

![image-20210803160552761](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210803160552761.png)



- 두 벡터 상의 거리를 이용하여 각도를 계산 ( *주의* : L2 노름에서만 가능)
- 내적 계산 (numpy.inner 이용)

![image-20210803161003827](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210803161003827.png)



## 내적

- 정사영된 벡터의 길이

  (정사영이란? 그림자로 생각하면 된다.)

- Proj(x) 의 길이는 코사인법칙에 
  $$
  ||x||cos(\theta)
  $$

- 두 벡터의 유사도(similarity)를 측정하는데 사용

- 벡터 y의 길이 ||y||만큼 조정한 값이다

![image-20210803161228754](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210803161228754.png)












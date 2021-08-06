# Gradient Descent(순한맛)

## 미분

- python에서 미분을 계산하는는 방법
- 어느 방향으로 증감하는지 알 수 있다.

```python
import sympy as sym
from sympy.abc import x

sym.diff(sym.poly(x**2 + 2*x + 3), x)
```

![image-20210804121734860](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804121734860.png)



- 미분값을 더하면 경사 상승법 -> 극대값을 구할 때 사용
- 미분값을 빼면 경사 하강법 -> 극소값을 구할 때 사용
- 극값에 도달하면 움직임을 멈춘다.



## 경사하강법

#### Input

- gradient : 미분을 계산하는 함수
- init : 시작 점
- lr : 학습률 (미분을 통해 업데이트하는 속도 조절)
- eps : 알고리즘 종료조건 (정확히 0이 되는 것은 불가능 하기 때문)

#### Output

- var

```python
var = init
grad = gradient(var)
while(abs(grad) > eps):
    var = var - lr * grad
    grad = gradient(var)
```





## 변수가 벡터인 경우

- 미분은 **변수의 움직임에 따른 함수값의 변화를 측정하기 위한 도구**
- 벡터가 입력인 경우 **편미분**을 사용.

![image-20210804123044565](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804123044565.png)

```python
import sympy as sym
from sympy.abc import x, y

sym.diff(sym.poly(x**2 + 2*x*y + 3))
```



- ei는 i번째 값만 1이고 나머지는 0인 단위 벡터

![image-20210804123502660](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804123502660.png)



- 각 변수별로 편미분을 계산한 **그레디언트 벡터**를 이용하여 경사하강/경사상승법에 사용

![image-20210804123333210](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804123333210.png)



## 그레디언트 벡터

![image-20210804123629216](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804123629216.png)



![image-20210804123723172](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804123723172.png)

![image-20210804123705275](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210804123705275.png)



- 경사하강법: 알고리즘

```python
var = init
grad = gradient(var)
while(norm(grad) > eps):
    var = var - lr * grad
    grad = gradient(var)
```



## 궁금한점 

- 그레디언트는 왜 노름을 이용할까?




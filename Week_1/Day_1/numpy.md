처음 부스트캠프를 활동하며 갈피를 잡지 못하는 와중 slack에서 크리스_운영진님께서 권장한 학습 가이드를 따라 1주차 동안 학습할 계획

8/2 (월)

- Python: 필수과제 1,2,3
- AI Math: 필수퀴즈 1~4강

8/3 (화)

- Python: 필수과제 4,5
- AI Math: 필수퀴즈 5~6강

8/4 (수)

- Python: 선택과제 1,2,3
- AI Math: 필수퀴즈: 7~9강

8/5 (목)

- AI Math: 필수퀴즈: 10강





8/2 (월)

- Python: 필수과제 1,2,3
- AI Math: 필수퀴즈 1~4강



numpy.array

- 한가지의 타입으로만 이루어져있다.
- List처럼 동적이지 않다.
- 데이터 할당 방식이 다르다.

![image-20210802150052505](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210802150052505.png)

numpy.ndarry의  shape

* row, column... 순으로 차원이 늘어날 수록 뒤로 밀려난다



numpy.reshape

- Array의 shape의 크기 변경, element 갯수 동일
![image-20210802151223815](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210802151223815.png)

numpy.flatten

- 한 줄로 늘린다



numpy.arange

- start,end,step으로 int 뿐만 아니라 floating point도 생성 가능하다.
- 일반적인 사용방법

![image-20210802151818368](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210802151818368.png)

numpy indexing

numpy slicing



numpy.zeros

numpy.ones

- 0, 1 로 가득한 ndarray로 생성



numpy.empty

- 메모리가 초기화는 되지 않는다 (쓰레기 값)

![image-20210802152235829](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210802152235829.png)



numpy.identity

- 단위 행렬 생성

numpy.eye

- 대각선이 1인 행렬, k값의 시작 index 변경 가능

numpy.diag

- 대각 행렬의 값을 추출함



numpy.random sampling

- 데이터 샘플링
- 종류
  - uniform
  - exponential
  - normal



numpy.sum

numpy.mean

numpy.std ...

[numpy mathematical]: https://numpy.org/doc/stable/reference/routines.math.html



axis(중요!!)

- 모든 operation function을 실행할 때 기준이 되는 dimension 축

![image-20210802153622155](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210802153622155.png)



numpy.concatenate

- vstack 
- hstack
- concatenate (axis에 따라)
- newaxis (하나의 축을 추가할 때 !!)

![image-20210802154343719](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210802154343719.png)

 Element-wise operations

- 같은 위치에 있는 element끼리 연산 (+, -, *)

Dot product

- Maxtrix의 기본 연산, dot 함수 사용

transpose

- 전치행렬 (행과 열의 위치를 바꾼다)

broadcasting

- shape이 맞지 않을 경우 값이 퍼진 다음 row와 column이 맞춰진 후 연산을 수행한다
- matrix-scalr 연산



timeit

- jupyter 환경에서 코드의 퍼포먼스를 체크하는 함수



Colab Command

Docstring : `shift + tab`
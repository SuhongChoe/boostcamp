# Convolution

-------------------

## 목표

- [ ] convolution 연산 방법과 기능
- [ ] 기본적인 CNN(Convolutional Neural Network) 구조
- [ ] Pytorch를 이용하여 CNN 실습

------------------------------------------------

### Continuous convolution

![image-20210811103539197](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210811103539197.png)

### Discrete convolution

![image-20210811103556246](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210811103556246.png)

### 2D image convolution

![image-20210811103615901](C:\Users\98dls\AppData\Roaming\Typora\typora-user-images\image-20210811103615901.png)



![image-20210811121620453](Convolution.assets/image-20210811121620453.png)

- 도장을 찍는다는 느낌으로 해석하면 좋음



![image-20210811121713406](Convolution.assets/image-20210811121713406.png)



## RGB Image Convolution

-----------------------

![image-20210811121833136](Convolution.assets/image-20210811121833136.png)

![image-20210811122008001](Convolution.assets/image-20210811122008001.png)

- 4개의 필터를 통과하면 4개의 feature가 나온다



## Stack of Convolution

-------------------------



![image-20210811122109282](Convolution.assets/image-20210811122109282.png)





## Convolutional Neural Networks

------------------------

![image-20210811122452817](Convolution.assets/image-20210811122452817.png)

- 일반적인 CNN의 형태
- parameter의 수가 늘어나면 학습시키기 어렵고 일반화 시키기 힘들다. => parameter를 줄이는 쪽으로 해야함



## Convolution Arithmetic (of GoogLeNet)

--------------------------

![image-20210811122806330](Convolution.assets/image-20210811122806330.png)

- [ ] 어떤 Neural Network에 대해서 parmeter가 몇개인지 손으로 계산해보고 표로 나온것이 진짜 맞는지 확인해보자



## Stride

---------------------------

![image-20210811122931708](Convolution.assets/image-20210811122931708.png)

- python [for 반복문]에서 step 느낌 => stride 수만큼 filter를 건너뜀



## Padding

------------------------

![image-20210811123059058](Convolution.assets/image-20210811123059058.png)





## Covolution Arithmetic

----------------------------------------

![image-20210811123651524](Convolution.assets/image-20210811123651524.png)





## Exercies : AlexNet

---------------------------------------

![image-20210811124246346](Convolution.assets/image-20210811124246346.png)

- pooling connect layer가 들어가 있기 때문에 뒷단에 있는 pooling connect layer를 최대한 줄이고 앞단에 covolution layer를 깊게 쌓는것이 일반적



![image-20210811125207370](Convolution.assets/image-20210811125207370.png)

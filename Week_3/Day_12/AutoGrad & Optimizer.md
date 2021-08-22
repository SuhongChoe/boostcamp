# AutoGrad & Optimizer

-----------------

## 목표

- [ ] Module과 Parameter가 어떤 역할을 하는지 알기
- [ ] Backward 구현해보기
- [ ] 모델 학습과정을 정리하고 성능을 올리는 방법에 대해 생각하기
- [ ] optimizer.zero_grad()와 batch step의 하는 역할이 뭔지 알기

---------------------

## 논문 = 수많은 반복의 연속

- Layer = Block



## torch.nn.Module

------------------------

- 딥러닝을 구성하는 Layer의 base class(autu_grad)
- Input, Ouput, Forwad, Backward(weight) 정의
- 학습의 대상이 되는 parameter 정의

![image-20210823024459570](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210823024459570.png)



## nn.Paramter

-----------------------------

- nn.Modlue 내에 **attribute가 될 때** required_grad = True 로 지정되어 학습 대상이 되는 Tensor



## Backward

-------------------

- model의 예측치를 foward 함수에 넣어준다



## Backward from the scratch

-----------------------

- 실제 backward는 Module 단계에서 지정가능(보통 auto_grad)
- 순서에 대해서는 이해할 필요가 있다


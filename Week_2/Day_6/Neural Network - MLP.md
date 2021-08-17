# 뉴럴 네트워크 - MLP

## 목표

- [x] Neural Networks 와 Deep nerual Networks의 개념과 직관적 이해
- [x] MLP 실습
- [ ] Regression Task, Classification Task, Probabilistic Task의 Loss function는 Pytorch에서 어떻게 구현이 되어있을까?



## Neural Networks

- 인간의 뇌를 모방했다라고 표현을 많이 한다.
- 모방을 하였지만 성능을 더 내기 위해서 수학적으로 모델을 개발하여 인간의 뇌를 모방하는 것과는 많이 바뀌어왔다는 것이 교수님의 생각



## Linear Neural Networks

![image-20210809115321056](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210809115321056.png)

### backpropagation

- W

![image-20210809115637433](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210809115715404.png)

- b 

![image-20210809115715404](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210809115637433.png)

- 두 개의 벡터 스페이스 사이를 연결해주는 W 행렬

![image-20210809120846065](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210809120846065.png)

- 어떻게 네트워크를 쌓을까?

![image-20210809120921150](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210809120921150.png)

![image-20210809121019428](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210809121532046.png)

- 뉴렬 네트워크는 다양한 함수를 표현할 수 있다 하지만 어떻게 찾는지는 모른다.



## MLP

![image-20210809121532046](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210809121019428.png)

- w의 개수 => layer 개수



## loss functions

![image-20210809123417716](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210809123417716.png)

- 보이는 각각의 loss function은 잘 사용하는 loss function 이지만 각각의 특징들을 알고 해결하고자 하는 문제에 적용시킬 때 loss function의 특징을 잘 고려하여 사용하는것이 좋다.
- 예를 들어 MSE는 제곱의 형태를 취했기 때문에 만약 값이 튀는 데이터가 있다면 그 데이터 하나만을 위해서 모델이 움직이기 때문에 망가질 가능성이 있다. 이때 MSE 보다는 MSA를 이용하는 것이 더 현명하다.
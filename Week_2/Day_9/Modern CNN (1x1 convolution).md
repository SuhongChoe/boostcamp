# Modern CNN - 1x1 convolution

## 목표

- [x] 주요 네트워크에 대해 배우기
- [ ] pytorch를 통해 어떻게 불러 올수 있을까?



## AlexNet

![image-20210817034816691](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817034816691.png)

- network가 두개 (=2개의 GPU)
- 5 convolution layers + 3 dense layers
- ReLU activation function
- Data augmentation
- Dropout



## VGGNet

<img src="https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817035351459.png" alt="image-20210817035216383" style="zoom:150%;" />

- 3 * 3 convolution을 활용한 것(중요)

  - 왜 3 * 3 일까?

  ![image-20210817035351459](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817035216383.png)

  3 by 3 두번 활용한것이 5 by 5를 한번 이용한 것 보다 parameters의 수가 적다



## GoogLeNet

![image-20210817035733462](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817035755030.png)

- NIN구조 (Network in Network)
- Inception Blocks

![image-20210817035755030](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817035733462.png)

- 1 by 1을 왜 사용할까? - **channel 방향으로 차원을 줄이는 효과**가 있다

![image-20210817035956753](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817035956753.png)



## ResNet

- 네트워크가 깊어짐에 따라 학습이 안되던 문제를 해결함

![image-20210817040646539](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817041016110.png)

​	=> Add Identity 



## DenseNet

![image-20210817041016110](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817040646539.png)

![image-20210817041042310](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817041042310.png)

- Dense Block => Transition Block

2배로 파라미터를 늘린다.



## Summary

- VGG - repeated 3 by 3 blocks
- GoogLeNet - 1 by 1 convolution
- ResNet - skip-connection
- DenseNet - concatenation


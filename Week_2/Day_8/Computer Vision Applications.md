# Computer Vision Applications

----------------------------

## 목표

------------------------------------

- [ ] CV에서 CNN이 이용한 분야에 대해 정의, 핵심 아이디어에 대해 이해하기
  - [ ] Semantic segmentation
  - [ ] Object detection



## Semantic segmentation (per pixel)

--------------------

![image-20210817060905958](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817060905958.png)

- 이미지의 모든 픽셀이 어떤 라벨에 해당하는지 찾는것이 목표

### Fully Convolutional Network

--------------------------------------------

- 기존 CNN

![image-20210817061042870](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817061042870.png)

- Fully Convolutional Network

![image-20210817061441265](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817061441265.png)

- CNN vs Fully CN(parameter수는 같다)

![image-20210817061622263](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817061622263.png)

- 왜 이렇게 할까?

![image-20210817061823863](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817061940616.png)



### Deconvolution (conv traspose)

-----------------------

![image-20210817061940616](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817061823863.png)

![image-20210817062114392](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817062700231.png)

- stride를 크게 주어서 Deconvolution을 구한다



### Results

-------------------------

![image-20210817062407651](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817062407651.png)



## Detection(bounding box)

-------------------------------

### R-CNN

-------------------------

![image-20210817062700231](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817062114392.png)

1) 이미지 안에서 bounding box 여러개 뽑는다
2) region에 대한 feature를 CNN, AlexNet을 통해 얻는다
3) L SVM을 통한 분류를 하자



### SPPNet

---------------

R-CNN와 다르게 이미지안에서 CNN이 한번만 돌아가게 만들자 해서 만들어짐

![image-20210817101228890](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817101639761.png)

뒷단에 Rol feature을 달았다는게 큰 의미가 된다



### Faster R-CNN (RPN)

------------------------------

![image-20210817101639761](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817101842660.png)

- Fatser R-CNN = **Region Proposal Network** + Fast R-CNN

   					![image-20210817101802269](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817101228890.png)

- bounding box에서 의미있는 이미지가 있는지 판단하는 것

![image-20210817101842660](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817102406340.png)

- 9 : Three different region sizes
- 4: four bounding box regression parameters
- 2: box classification (쓸모있는지 없는지)



### YOLO

-------------------------------------------------------

- RPN에서는 bounding box에 대해 따로 분류를 해주었지만 YOLO에서는 bounding box를 따로 뽑는 과정이 한번에 처리되도록 설계되었기 때문에 더 빠르다

![image-20210817102406340](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817101802269.png)

1-1. bounding box가 몇개인지 찾음

1-2. grid cell이 bounding box가 어떤 클래스에 속하는지 찾음

2. 결과 도출




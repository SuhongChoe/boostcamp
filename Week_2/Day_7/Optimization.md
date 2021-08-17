# Optimization

## 목표

- [x] Generalization,Overfitting, Cross-validation 각각의 의미에 대해 알기
- [x] 다양한 GD에 대해 이해하고 체화하기
- [x] 올바른 cross-vaildation
- [ ] Time series의 경우 일반적인 k-fold cv를 사용해도 될까?
- [ ] [RAdam](https://github.com/LiyuanLucasLiu/RAdam)
- [ ] [AdamP](https://github.com/clovaai/AdamP)



## Optimization

- Generalization
- Under-fitting vs. over-fitting
- Cross validation
- Bias-variance tradeoff
- Bootstrapping
- Bagging and boosting



## Generalization

![image-20210810123053585](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810123053585.png)

- 성능이 잘나온다가 아닌 학습데이터와 테스트 데이터 사이에 얼마나 차이가 나는지를 확인



## underfitting 

- 네트워크가 너무 간단하거나 train을 너무 조금 시켜서 학습도 안된것

## overfitting

- 학습데이터에 대해서는 잘 동작하지만 테스트데이터에서는 동작을 잘 안함(그림은 약간 컨셉적인 이야기)

![image-20210810123357859](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810123357859.png)



## Cross-validation

- 최적의 하이퍼파라미터를 찾고 값을 고정시킨 후 모든 데이터를 사용함
- 테스트데이터로 validation을 한다는 것은 그 자체로 치팅임 => 테스트 데이턴튼 어떤 식으로든 활동하면 안됨



## Bias and Variance

![image-20210810124112352](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810124112352.png)

- Variance 내가 어떤 입력을(또는 비슷한 입력을) 넣었을때 출력이 얼마나 일관적으로 나오는지
- Bias 비슷한 입력에 대하여 분산이 크더라도 평균적으로 봤을때는 target에 가까우면 Bias가 낮다고 표현



## Bias and Variance Tradeoff

![image-20210810124446608](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810124726763.png)

- 이해가 잘 되지 않음



## Bootstrapping

![image-20210810124726763](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810125641724.png)

- 데이터중 다 사용하지 않고 몇개만 사용해서 모델을 만들겠다



### Bagging vs. Boosting

![image-20210810125147273](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810124446608.png)



## Practical Gradient Descent Methods

- SDG - 하나의 샘플을 통해서 GD를 업데이트
- Mini-batch GD - 배치를 뜯어서 GD를 업데이트 (대부분 Mini-batch를 선호)
- Batch DG - 한번에 GD를 업데이트



### Batch-size Matters

- sharp minimizers 보다 flat minimizer에 도닿하는 것이 더 좋다

![image-20210810125641724](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810125147273.png)



## Gradient Descent Methods

- Stochastic gradient descent
- Momentum
- Nesterov accelerated gradient
- Adagrad
- Adadelta
- RMSprop
- Adam



### 1. (Stochastic) Gradient descent

![image-20210810132213548](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810132213548.png)

### 2. Momentum

![image-20210810132349839](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810132645358.png)

- 한번 흘러간 GD를 어느정도 유지 시켜주기 때문에 왔다 갔다 해도 어느정도 잘 학습이 되는 효과



### 3. Nesterov accelerated gradient

![image-20210810132645358](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810133634061.png)

###  4. Adagrad

![image-20210810133634061](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810132349839.png)

- 많이변한 파라미터는 작게, 작게변한 파라미터는 크게 변화
- 문제점 - 뒤로가면 갈수록 학습이 멈춰짐



### 5. Adadelta

![image-20210810133905661](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810133905661.png)

- learning rate가 없다 -> 바꿀 파라미터가 없다 -> 잘 사용하지 않음



### 6. RSMprop

![image-20210810134136879](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810134136879.png)



### 7.  Adam (Adaptive Moment Estimation)

![image-20210810134434970](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810134723588.png)

- momentum을 잘 섞은 것



## Regularization - 학습을 방해함으로써 학습데이터 뿐만 아니라 데스트데이터에서 잘 동작하게끔 만들어줌

- Early stopping
- Parameter norm penalty
- Data augmentation
- Noise robustness
- Label smoothing
- Dropout
- Batch normalization



### Early stopping

![image-20210810134723588](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810134828840.png)



### Parameter Norm Penalty

![image-20210810134828840](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810134434970.png)

- 학습할때 네트워크 W가 크기 관점에서 작게하자
- 뉴럴네트워크 함수공간속에서 부드러운 함수로 바라보자



### Data Augmentation

![image-20210810135042655](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810135042655.png)

- label이 변하지 않는 조건에서 하는것이 중요

![image-20210810135803648](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810135239086.png)



### Noise Robustness

![image-20210810135239086](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810135803648.png)



### Label Smoothing

![image-20210810135321479](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810140150957.png)

- 분류문제를 푼다 , 데이터셋 한정적 => Mixup, Cutout, CutMix를 사용해 보자



### Dropout

![image-20210810135844058](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810135321479.png)



### Batch Normalization (논란이 많음)

- 내가 적용하고자 하는 레이어에 스테트틱스를 정규화 하는것
- 논란이 많지만 분류문제에 경우 성능이 올라가긴 함

![image-20210810140150957](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210810135844058.png)


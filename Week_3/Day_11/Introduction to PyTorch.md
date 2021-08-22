# PyTorch

-----------------------------

## 목표

--------------------------------

- [x] PyTorch의 기본적인 작동 구조에 대해 학습



자주 사용되는 딥러닝 프레임워크

TensorFlow와 PyTorch의 차이점은 computational graphs used(**auto-gradient**)에서 차이가 난다.

- TensorFlow : Static graphs(= Define and run)
- PyTorch : Dynamic computation graphs



## Computational Graph

---------------------------------------

- 연산의 과정을 그래프로 표현

$$
g=(x+y)*z
$$

![image-20210817143402952](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817143402952.png)

- Define and Run
  - 그래프를 먼저 정의 -> 실행시점에 데이터 feed
- Define by Run(Dynamic Computational Graph, **DCG**)
  - 실행을 하면서 그래프를 생성하는 방식
  - Debug에서 굉장이 편하다



## Why PyTorch

---------------

- Define by Run 의 장점
  - 즉시 확인 가능 -> pythonic code
- GPU support, Good API and community
- 사용하기 편한 장점이 가장 큼
- TF는 production, scalability, Cloud, Muti-GPU의 장점



## PyTorch

----------------------------

Numpy + AutoGrad + Function

- Numpy 구조를 가지는 Tensor 객체로 array표현
- 자동미분을 지원
- 다양한 형태의 DL을 지원하는 함수와 모델 (Dataset, Muit-GPU)
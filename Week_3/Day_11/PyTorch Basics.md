# PyTorch Basics

----------------------

## 목표

-------------------

- [ ] Tensor 사용법
- [ ] AutoGrad
- [ ] Custom Network 작성할 수 있는 기본지식
- [ ] AutoGrad를 통해 backward 함수가 학습시 어떻게 동작하는지 확인



## Tensor

--------------------------

```python
"""
numpy - ndarray
"""
import numpy as np
n_array = np.arange(10).reshape(2,5)
print(n_array)
print("ndim :", n_array.ndim, "shape :", n_array.shape)

"""
pytorch - tensor
"""
import torch
t_array = torch.FloatTensor(n_array)
print(t_array)
print("ndim :", t_array.ndim, "shape :", t_array.shape)
```

- Tensor 생성은 list나 ndarray를 사용 가능

```python
"""
data to tensor
"""
data = [[3, 5],[10,5]]
x_data = torch.tensor(data)
x_data

"""
ndarray to tensor
"""
nd_array_ex = np.array(data)
tensor_array = torch.from_numpy(nd_array_ex)
tensor_array
```



- 기본적으로 tensor가 가질 수 있는 data 타입은 numpy와 동일(GPU에서 차이가 난다)

```python
data = [[3,5,20],[10,5,50],[1,5,10]]
x_data = torch.tensor(data)

x_data[1:]

x_data[:2, 1:]

x_data.flatten()

torch.ones_like(x_data) # [[1,1,1],[1,1,1],[1,1,1]]

x_data.numpy()

x_data.shape

x_data.dtype
```



- pytorch의 tensor는 GPU에 올려서 사용가능

```python
x_data.device
# device(type='cpu')

if torch.cuda.is_availble():
    x_data_cuda = x_data.to('cuda')
x_data_cuda.device
# device(type='cuda', index=0)
```



### Tensor handling

-------------------------

- view: reshape과 동일하게 tensor의 shape을 변환
- squeeze: 차원의 개수가 1인 차원을 삭제 (압축)
- unsqueeze: 차원의 개수가 1인 차원을 추가



![image-20210817151520514](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817151520514.png)



### Tensor operations

-------------

![image-20210817151905420](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210817151905420.png)



1. torch에서 tensor는 numpy와 동일하다
2. reshape대신에 view 사용할
3. squeeze와 unsqueeze의 차이를 이해하라 



## AutoGrad

-----------------------

Pytorch의 핵심은 **자동 미분**의 지원 -> backward 함수 사용
$$
y = w^2
$$
$$
z = 10*y + 25
$$
$$
z = 10*w^2 + 25
$$


```python
w = torch.tensor(2.0, requires_grad=True)
y = w**2
z = 10*y + 2
z.backward()
w.grad
```


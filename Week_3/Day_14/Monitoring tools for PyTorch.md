# Monitoring tools for PyTorch

--------------------

## 목표

- [ ] Tensorboadr, weight & biases 학습



## 긴 학습 시간 기다림의 기록이 필요

=> 좋은 도구들을 사용하자

![image-20210823031721354](https://raw.githubusercontent.com/choesuhong/save-image-repo/image/img/image-20210823031721354.png)



## Tensorboard

----------------------------

- TensorFlow의 프로젝트로 만들어진 시각화 도구
- 학습 그래프, metric, 학습 결과의 시각화 지원
- PyTorch도 연결 가능 -> DL 시각화 핵심 도구

- scalar : metric 등 상수 값의 epoch을 표시
- graph : 모델의 computational graph 표시
- histogram : weigh 등 값의 분포를 표현
- image : 에측 값과 실제 값을 비교 표시
- mesh : 3d 형태의 데이터를 표현하는 도구



## weight & biases

-----------------------------

- 머신러닝 실험을 원활히 지원하기 위한 상용도구
- 협업, code versioning, 실험 결과 기록 등 제공
- MLOps의 대표적인 툴
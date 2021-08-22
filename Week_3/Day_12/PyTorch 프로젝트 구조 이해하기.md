# PyTorch Project Template Overview

---------------

## 목표

------------------

- [ ] OOP와 모듈의 개념을 통해 프로젝트를 구성하는 방법
- [ ] PyTorch에서 구성되는 모듈 확인
- [ ] PyTorch 사용법
- [x] VSCode와 SSH로 연결해서 Colab을사용하는 방법



- 초기단계에서 대화식 개발 과정이 유리
  - 학습과정과 디버깅 등 지속적인 확
- 배포 및 공유 단계에서는 notebook 공유의 어려움
  - 쉬운 재현의 어려움, 실행순서 꼬임
- DL 코드도 하나의 프로그램
  - 개발 용이성 확보와 유지보수 향상 필요



코드도 레고블럭 처럼 **OOP + 모듈 = 프로젝트**



### PyTorch Template  추천

--------------------

- https://github.com/FrancescoSaverioZuppichini/PyTorch-Deep-Learning-Template
- https://github.com/PyTorchLightning/deep-learning-project-template
- https://github.com/victoresque/pytorch-template



## Module 구성

--------------------------

- 실행
- 설정
- base - abstract module
- data
- model - architecture, loss, metric
- 저장소 -로그, 모델상태
- 학습 수행
- 로깅설정
- 유틸리티



## Project의 코드를 따라가면서 이해해보기 (주석으로 메모)
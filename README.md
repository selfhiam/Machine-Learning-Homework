# Machine-Learning / Homework

# 1. 부스팅(Boosting)
* 여러 개의 약한 학습기(Weak Learners)를 순차적으로 학습시켜, 각각의 예측을 결합하여 더 강력한 최종 모델을 만드는 기법
* 초기 전체 데이터에 대한 학습을 진행. 이후 생성되는 학습기는 이전 학습기가 잘못 예측한 데이터에 대해 더 많은 가중치를 두고 학습을 진행.
* 해당 과정을 반복하면서 모델은 점점 더 정확성이 높아짐

### 1-1. 부스팅의 종류

* AdaBoost
    * 간단한 결정 트리를 기반으로 하여, 각각의 반복에서 데이터 포인트에 가중치를 적용.
    * 잘못 분류된 데이터 포인트에 더 높은 가중치를 부여하고, 이를 바탕으로 새로운 학습기를 훈련.
    * 해당 과정이 반복될수록 모델은 점점 더 복잡하고 정확해 진다.

* XGBoost
    * 기울기 부스팅(Gradient Boosting)의 한 형태로, 효율적인 계산과 높은 예측 성능을 자랑
    * 각 단계에서 손실 함수의 기울기를 사용하여 모델을 업데이트
    * 병렬처리, 트리 가지치기, 교차 검증 등의 기능을 포함함.

# 2. 스태킹(Stac king)
* 스태킹은 여러 가지 다른 모델을 조합하여 새로운 모델을 생성하는 기법.
* 기본 모델(base models)의 예측 결과를 새로운 데이터 세트로 사용하여, 최종 결정을 내리는 메타 모델(meta-model)을 훈련.
* 다양한 종류의 모델들이 초기 예측을 수행, 해당 예측들을 입력 데이터로 하여금 최종 모델이 최종 예측을 수행

### 2-2. 스태킹의 종류
* 기본 모델의 훈련
    * 여러 다른 종류의 모델들을 별도로 훈련시킵니다. 해당 모델은 동일한 데이터 세트에 대해 학습을 수행하지만, 다른 접근 방식을 이용하여 훈련을 진행함.

* 메타 모델의 훈련
    * 기본 모델들의 예측을 새로운 '메타'데이터 세트로 사용하고, 이를 기반으로 메타 모델을 훈련함. 메타모델은 기본 모델들의 예측을 종합하여 최종 예측을 결정함.

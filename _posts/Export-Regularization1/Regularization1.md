---
title: (ML)Regularization
categories: [ML]
comments: true
---

# Regularization

# 1. The Problem Of Overfitting

![Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled.png](Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled.png)

위 그림은 Linear Regression의 주택 가격 예측에 대한 그래프이다.

첫번째는 1차방정식으로 표현되어 직선이 나오게 된다. 하지만 예측값과 실제값이 많이 다르기 때문에 underfit되었다고 한다. 또한 bias가 높다.

세번째는 4차방정식으로 표현되어 여러 굴곡을 가진 곡선이 나오게 된다. 예측값과 실제값이 많이 일치하지만 training data말고 test data에 적용하기에는 overfit되었다고 한다. 또한 variance가 높다.

두번째는 2차방정식으로 표현되는데 이 경우에 적합하게 최적화되었다고한다.

![Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%201.png](Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%201.png)

Logistic regression에서 또한 첫번째는 1차방정식으로 최적화가 덜 되어서 underfit, 세번째는 다항방정식으로 최적화가 과하게 되어 overfit, 두번째는 2차방정식으로 적절히 최적화되어 just right 이다.

Bias는 얼마나 떨어져 있는가를 나타내고, Variance는 얼마나 퍼져있는지를 나타낸다. 
overfitting이 일어날수록 variance가 높아지고, underfitting이 일어날수록 bias가 높아진다.
Bias와 Variance의 관계는 Trade off이다. 

MSE ⇒ Error(X) = noise(X) + bias(X) + variance(X)

noise는 irreducible error로 줄일 수 없는 에러이고 bias와 variance는 reducible error로 줄일 수 있는 에러이다. 따라서 bias와 variance를 둘 다 줄이기 위한 모델을 찾는 것이 목표이다.

## Overfitting

: If we have too many features, the learned hypothesis may fit the training set very well, but fail to generalize to new examples(predict prices on new examples)

: overfitting이란 많은 feature를 가지고 있을 때, training set은 너무 잘 맞출 수 있으나 새로운 데이터에 대해서는 일반화하기 어려워 가격을 예측하지 못하는 경우를 말한다. (복잡할수록 데이터가 작을수록 overfitting되기 쉽다)

### *overfitting을 줄이는 방법*

1. Reduce number of features

    feature의 수를 줄이면 overfitting을 줄일 수 있지만 중요한 feature를 버릴 수 있다.

2. Regularization

    모든 feature를 유지하면서 parameter의 크기를 줄여서 overfitting을 줄일 수 있따.

    y의 값에 더 많은 기여를 하는 feature에게 높은 비중을 두는 방법.

    - Example
        - 아래의 오른쪽 그래프는 4차 방정식으로 cost function의 min을 구하기 위해 세타3과 세타 4에 0에 가까운 아주 작은 수를 넣어준다. 따라서 왼쪽과 같이 2차방정식으로 overfitting을 줄일 수 있다.

            ![Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%202.png](Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%202.png)

- Linear Regression

$$H(x)=Wx+b$$

- Cost Function(=Loss Function) : How fit the line to our (training) data

    ⇒ cost값을 minimize하는 w,b를 구하는 것

![Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%203.png](Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%203.png)

## Regularization

![Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%204.png](Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%204.png)

![Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%205.png](Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%205.png)

parmeter 세타0에서 n까지 중에서 몇개의 parameter에 작은 값을 주면 조금 더 단순해지면서 overfitting을 줄일 수 있다. 따라서 그에 해당하는 λ식을 cost function뒤에 추가해주었다. 세타0는 상수이므로 세타1부터 n까지 제곱해준 값을 더해준다.

λ는 regularization parameter인데, λ는 두개의 서로 다른 목표 사이의 균형을 조절하는 역할을 한다.

첫번째는 fit training set이고 두번째는 parameter를 작은 값으로 바꿔 simple하게 하여 정규화를 하게 한다. 

⇒ λ식을 cost function 뒤에 추가하게 되면 overfitting을 줄여 훨씬 더 단순하게 할 수 있다.

- 또한 λ의 값을 잘 선택하는 것이 중요하다.

    ![Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%206.png](Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%206.png)

만약  λ의 값이 너무 커지게 되면 세타의 값들이 아주 작아져 세타0만 남게 되어 직선이 되는데,

이 때 underfit이 된다.

# Regularized linear regression

### Gradient descent algorithm ⇒ lowest point

- 미분 과정

    ![Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%207.png](Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%207.png)

따라서 gradient descent algorithm이 구해졌고, 여러번 반복함으로써 W의 값이 바뀌게 되는데

이때 cost function의 값이 minimize해지는 것이다.

위에서 미분하여 구한 값을 아래에 적용하여 뒤에 λ식을 추가하면 세타j가 아래와 같다.

- Gradient descent

    ![Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%208.png](Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%208.png)

세타j의 값은 1보다 작은 값을 계속 곱하므로 점점 작아지게 된다. 따라서 위의 과정을 통해 정규화가 된다.

### Normal equation

![Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%209.png](Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%209.png)

위의 식은 matrix의 오차제곱항을 나타낸다. matrix X는 m x (n+1)의 크기를 가진다.

normal equation을 사용하여 regularization을 하게 되면,

![Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%2010.png](Regularization%20eba8fa76fe1e403684caa8484ef9b1a5/Untitled%2010.png)

 λ식을 위의 식처럼 추가하게 되는데, 이 때  행렬은 좌측 제일 상단만 0이고 우측 대각선으로 모두 1로 구성되어 있으며 나머지 값들은 모두 0으로 구성되어 있다. 만약 n=2 ⇒ 3 x 3 크기의 matrix가 되고 matrix는 [0 0 0; 0 1 0; 0 0 1] 으로 구성된다.

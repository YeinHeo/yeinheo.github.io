---
title: (ML)Overfitting
categories: [ML]
comments: true
---


### The Problem Of Overfitting

![Untitled.png](/assets/img/20-10-09/Regularization/Untitled.png){: width="470" height="200"}

위 그림은 Linear Regression의 주택 가격 예측에 대한 그래프이다.

첫번째는 1차방정식으로 표현되어 직선이 나오게 된다. 하지만 예측값과 실제값이 많이 다르기 때문에 underfit되었다고 한다. 또한 bias가 높다.

세번째는 4차방정식으로 표현되어 여러 굴곡을 가진 곡선이 나오게 된다. 예측값과 실제값이 많이 일치하지만 training data말고 test data에 적용하기에는 overfit되었다고 한다. 또한 variance가 높다.

두번째는 2차방정식으로 표현되는데 이 경우에 적합하게 최적화되었다고한다.  


![Untitled%201.png](/assets/img/20-10-09/Regularization/Untitled%201.png){: width="450" height="225"}

Logistic regression에서 또한 첫번째는 1차방정식으로 최적화가 덜 되어서 underfit, 세번째는 다항방정식으로 최적화가 과하게 되어 overfit, 두번째는 2차방정식으로 적절히 최적화되어 just right 이다.

```
Bias는 얼마나 떨어져 있는가를 나타내고, Variance는 얼마나 퍼져있는지를 나타낸다.  
overfitting이 일어날수록 variance가 높아지고, underfitting이 일어날수록 bias가 높아진다.  
Bias와 Variance의 관계는 Trade off이다. 

MSE ⇒ Error(X) = noise(X) + bias(X) + variance(X)

noise는 irreducible error로 줄일 수 없는 에러이고,  
bias와 variance는 reducible error로 줄일 수 있는 에러이다.  
따라서 bias와 variance를 둘 다 줄이기 위한 모델을 찾는 것이 목표이다.
```

### Overfitting

: If we have too many features, the learned hypothesis may fit the training set very well, but fail to generalize to new examples(predict prices on new examples)

: overfitting이란 많은 feature를 가지고 있을 때, training set은 너무 잘 맞출 수 있으나 새로운 데이터에 대해서는 일반화하기 어려워 가격을 예측하지 못하는 경우를 말한다. (복잡할수록 데이터가 작을수록 overfitting되기 쉽다)

### Overfitting을 줄이는 방법

1. Reduce number of features

    feature의 수를 줄이면 overfitting을 줄일 수 있지만 중요한 feature를 버릴 수 있다.

2. Regularization

    모든 feature를 유지하면서 parameter의 크기를 줄여서 overfitting을 줄일 수 있다.

    => y의 값에 더 많은 기여를 하는 feature에게 높은 비중을 두는 방법.


-Example  

   아래의 오른쪽 그래프는 4차 방정식으로 cost function의 min을 구하기 위해 세타3과 세타 4에 0에 가까운 아주 작은 수를 넣어준다. 
   따라서 왼쪽과 같이 2차방정식으로 overfitting을 줄일 수 있다.  


   ![Untitled%202.png](/assets/img/20-10-09/Regularization/Untitled%202.png){: width="500" height="300"}  



- Linear Regression

    H(x)=Wx+b

- Cost Function(=Loss Function) : How fit the line to our (training) data  

    ⇒ cost값을 minimize하는 w,b를 구하는 것  
    
    ![Untitled%203.png](/assets/img/20-10-09/Regularization/Untitled%203.png){: width="250" height="50"}




### Reference
    
   [Lecture 7.1 — Regularization | The Problem Of Overfitting — (Machine Learning | Andrew Ng | Stanford University)](https://www.youtube.com/watch?v=u73PU6Qwl1I)

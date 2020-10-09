---
title: (ML)Regularization
categories: [ML]
comments: true
---


## Lasso Reression

Lasso Regression은 Ridge Regression인 **the sum of the squared residuals + λ (slope)^2**에서 
**the sum of the squared residuals + λ |slope|**으로 바뀐 것이다.

λ는 0에서 양의 무한대 사이의 값을 가지며 cross validation을 사용하여 결정된다.

### Lasso Regression vs Ridge Regression
  Ridge Regression

        ![Untitled%202.png](/assets/img/20-10-09/Regularization2/Untitled%202.png){: width="100" height="25"}

  Lasso Regression

        ![Untitled%203.png](/assets/img/20-10-09/Regularization2/Untitled%203.png){: width="100" height="25"}


- 비슷한점

        λ값이 0이 되면 Least Squares Line과 같아지고, λ값이 점점 증가하고 slope값이 점점 작아지다가 결국 0이 된다.

- 다른 점

        Ridge Regression은 점차적으로 slope이 0이 되는데 Lasso Regression은 t값을 줄이는 과정에서 중요하지 않은 변수가 t가 0이 되기 전에 바로 0이 된다. 

        또한 Ridge는 모서리(x축이나 y축)에서 정답(MSE랑 만나는 지점-제약조건을 만족하면서 MSE가 최소가 되는 지점)이 나타나지 않는데, Lasso는 절대값이므로 마름모 형태로 나타나게 되는데 이 경우에는 정답이 모서리에서 나타나 관련없는 변수값을 0으로 만든다. 아래는 베타1의 값이 0이 되는 것을 보아 베타1은 중요하지 않다는 것을 알 수 있다.

        ![Untitled%204.png](/assets/img/20-10-09/Regularization2/Untitled%204.png){: width="400" height="200"}

        왼쪽이 Ridge Regression, 오른쪽이 Lasso Regression


- Lasso Regression

![Untitled%205.png](/assets/img/20-10-09/Regularization2/Untitled%205.png){: width="300" height="45"}

LASSO : Least Absolute Shrinkage and Selection Operator

Lasso Regression: Y를 예측하는데 중요한 x를 자동으로 선택하는 모델이다. Ridge Regression의 shrinkage에 selection이 더해진 것이다. 따라서 Lasso는 필요없는 변수들을 줄여 모델의 variance를 줄여준다.


### Summary

Ridge Regression is very similar to Lasso Regression. 

The superficial difference is that Ridge Regression squares the variables and Lasso Regression takes the absolute value. But the big difference is that Lasso Regression can exclude useless variables from equations. 

⇒ simpler and easier to interpret

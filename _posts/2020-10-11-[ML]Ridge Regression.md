---
title: (ML)Ridge Regression
categories: [ML]
comments: true
---


## Ridge Regression

- Least Squares 한계점

    만약 2개의 training data가 있다면 어떻게 될까?

    아마도 least squares를 사용하여 2개의 training data를 지나는 line을 그려 sum of the squared residuals을 0으로 만들 수 있다. 하지만 testing data가 많아질수록 line에 적합하지 않아 sum of the squared residuals은 매우 커지게 되고, line은 high variance를 가진다. 우리는 least squres를 통해 line이 overfit되고 high variance를 가진다는 것을 확인할 수 있다. 이와 같은 한계점으로 Ridge Regression을 통해 적합한 line을 찾는 방법을 고려하게 되었다.

### Least Squares   vs   Ridge Regression

- Least Squares: minimize the sum of the squared residuals

- Ridge Regression: minimize the sum of the squared residuals + λ (the slope)^2


![Untitled.png](/assets/img/20-10-09/Regularization2/Untitled.png){: width="360" height="60"}

   Ridge Regression은 실제 Y값에다 MSE를 최소화시키는데 베타 제곱을 특정한 값보다 작게 제약하는 것이다.

   <u>**λ (slope)^2  ⇒ Ridge Regression Penalty**</u>

   slope 제곱은 기존 least squares에 penalty를 더하고, λ는 얼마나 penalty를 줄 것인가를 결정한다.

![Untitled%201.png](/assets/img/20-10-09/Regularization2/Untitled%201.png){: width="150" height="200"}

   빨간색: Least Squres  
   파란색: Ridge Regression

⇒ 위와 같이 Ridge Regression을 사용하면 variance가 적어진다.  




- **slope**
    : Least Squares Line보다 Ridge Regression Line이 경사가 더 완만하므로 weight의 변화에 따른 size의 변화가 less sensitive하다.

- **λ**
    : 만약 0이면 least squares와 같아지고, 큰 값을 가지면 slope이 0에 가까워지므로 least squares와 같아진다.

    - 큰 λ 값: 간단한 모델, underfit 위험 증가
    - 작은 λ 값: 복잡한 모델, overfit 위험 증가


&#42; 만약 training set에 only one datapoint가 있다면 Least Squares는 optimal solution을 찾지 못하지만
Ridge Regression은 cross validation 과 Ridge Regression penalty로 solution을 찾을 수 있다.

### Summary

This is done by adding the <u>Ridge Regression Penalty</u> to the thing that must be minimized
<u>**the sum of the squared residuals__ + __λ (slope)^2**</u>

λ is determined using Cross Validation.

When there isn't enough data to find the Least Squares parameter estimates, 
Ridge Regression can still find a solution with Cross Validation and Ridge Regression Penalty.



### Reference 

- https://www.youtube.com/watch?v=Q81RR3yKn30  
  [Regularization Part 1: Ridge (L2) Regression]

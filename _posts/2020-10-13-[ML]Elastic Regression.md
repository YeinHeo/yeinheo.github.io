---
title: (ML)Elastic Regression
categories: [ML]
comments: true
---


## Elastic Net Regression

Lasso Regression은 변수들 간의 상관관계가 클 경우에 변수 선택 성능이 저하될 수 있다. 따라서 상관 관계 큰 변수를 동시에 선택하거나 배제하는 특성을 가진 Elastic Net Regression을 알아보자!

- Elastic Net Regression

    ![Untitled%206.png](/assets/img/20-10-09/Regularization2/Untitled%206.png){: width="360" height="60"}

    Elastic Net Regression = **Lasso Regression + Ridge Regression**

    => good at dealing with situations when there are correlations between parameters



    Elastic net estimator에 대해 다음 부등식이 성립된다.(x(i)와 x(j)는 상관계수)
    ![Untitled%207.png](/assets/img/20-10-09/Regularization2/Untitled%207.png){: width="300" height="50"}

    p(ij)가 1이 되면 좌측항은 0보다 작거나 같게 되는데 이때 베타i와 베타j가 같게 된다. 또한 람다2가 큰 값을 가지게 되어도 베타i와 베타j의 상관관계가 커진다.

    ⇒ Grouping effect라고 해서 correlation을 고려한다. 
    


### Summary

    <u>Elastic-Net Regression combines the Lasso Regression Penalty with the Ridge Regression Penalty.</u>
    It does a better job dealing with correlated parameters.
    


### Reference 

- https://www.youtube.com/watch?v=Q81RR3yKn30  
  [Regularization Part 3: Elastic Net Regression]
  

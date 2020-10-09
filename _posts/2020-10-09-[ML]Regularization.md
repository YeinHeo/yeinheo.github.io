---
title: (ML)Regularization
categories: [ML]
comments: true
---


# Regularization

![Untitled%204.png](/assets/img/20-10-09/Regularization/Untitled%204.png){: width="250" height="25"}

![Untitled%205.png](/assets/img/20-10-09/Regularization/Untitled%205.png){: width="320" height="70"}

parmeter 세타0에서 n까지 중에서 몇개의 parameter에 작은 값을 주면 조금 더 단순해지면서 overfitting을 줄일 수 있다. 따라서 그에 해당하는 λ식을 cost function뒤에 추가해주었다. 세타0는 상수이므로 세타1부터 n까지 제곱해준 값을 더해준다.

λ는 regularization parameter인데, λ는 두개의 서로 다른 목표 사이의 균형을 조절하는 역할을 한다.  
첫번째는 fit training set이고, 두번째는 parameter를 작은 값으로 바꿔 simple하게 하여 정규화를 하게 한다. 

=> λ식을 cost function 뒤에 추가하게 되면 overfitting을 줄여 훨씬 더 단순하게 할 수 있다.  



- 또한 λ의 값을 잘 선택하는 것이 중요하다.

    ![Untitled%206.png](/assets/img/20-10-09/Regularization/Untitled%206.png){: width="400" height="200"}

    만약  λ의 값이 너무 커지게 되면 세타의 값들이 아주 작아져 세타0만 남게 되어 직선이 되는데, 이 때 underfit이 된다.



## Regularized linear regression

### Gradient descent algorithm ⇒ lowest point

- 미분 과정

    ![Untitled%207.png](/assets/img/20-10-09/Regularization/Untitled%207.png){: width="400" height="200"}

    따라서 gradient descent algorithm이 구해졌고, 여러번 반복함으로써 W의 값이 바뀌게 되는데, 이때 cost function의 값이 minimize해지는 것이다.

    위에서 미분하여 구한 값을 아래에 적용하여 뒤에 λ식을 추가하면 세타j가 아래와 같다.

- Gradient descent

    ![Untitled%208.png](/assets/img/20-10-09/Regularization/Untitled%208.png){: width="450" height="270"}

    세타j의 값은 1보다 작은 값을 계속 곱하므로 점점 작아지게 된다. 따라서 위의 과정을 통해 정규화가 된다.

### Normal equation

![Untitled%209.png](/assets/img/20-10-09/Regularization/Untitled%209.png){: width="200" height="35"}

위의 식은 matrix의 오차제곱항을 나타낸다. matrix X는 m x (n+1)의 크기를 가진다.

normal equation을 사용하여 regularization을 하게 되면,

![Untitled%2010.png](/assets/img/20-10-09/Regularization/Untitled%2010.png){: width="500" height="150"}

 λ식을 위의 식처럼 추가하게 되는데, 이 때  행렬은 좌측 제일 상단만 0이고 우측 대각선으로 모두 1로 구성되어 있으며 나머지 값들은 모두 0으로 구성되어 있다. 만약 n=2 ⇒ 3 x 3 크기의 matrix가 되고 matrix는 [0 0 0; 0 1 0; 0 0 1] 으로 구성된다.

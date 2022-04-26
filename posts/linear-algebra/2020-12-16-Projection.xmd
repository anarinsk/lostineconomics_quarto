---
layout: post
toc: false
comments: true
title:  Projection and Distance 
description: 프로젝션과 거리 측정에 관해 알아보자.
categories: [math, matrix-theory]

---

## Projection: Scalar and Vector  

### Definition 

다음과 같은 두 개의 벡터, $\vec a$, $\vec b$를 일단 떠올려보자. 

![enter image description here](https://upload.wikimedia.org/wikipedia/commons/9/98/Projection_and_rejection.png){: style="margin: auto; display: block; border:1.5px solid #021a40;"}{: width="300"}

스칼라 프로젝션 $a_1$의 정의는 다음과 같다. 

$$
a_1 ={\cos \theta}{\lVert \vec a \lVert} = \lVert \vec a_1 \lVert 
$$

각 $\theta$에 관해서 다음과 같이 정의할 수 있다. 혹시 리마인드가 필요하면 포스팅 [dot product](https://anarinsk.github.io/lostineconomics-v2-1/math/2019/07/18/dot-product.html)를 참고하라. 

$$
\cos \theta = \dfrac{\vec a \cdot \vec b}{\lVert \vec a \lVert \lVert \vec b \lVert}
$$

그리고 

$$
\hat b = \dfrac{\vec b}{\lVert \vec b \lVert}
$$

라고 할 때, 

$$
a_1 = {\cos \theta}{\lVert \vec a \lVert} = \dfrac{\vec a \cdot \vec b}{\lVert\vec b\lVert} = \vec a \cdot \hat b
$$

쉽게 말해서, $\vec a$ 벡터와 정규화된 $\vec b$의 닷프로덕트라고 생각하면 된다. 

### Vector projection 

스칼라 프로젝션의 크기로 $\vec b$의 벡터를 만든 것이 벡터 프로젝션이다. $\vec a$를 $\vec b$ 위로 프로젝션한 벡터 $\Pi_{\vec b} (\vec a)$는 다음과 같다. 

$$
\vec a_1 = \Pi_{\vec b} (\vec a) = a_1 \hat b = \dfrac{\vec a \cdot \vec b}{\lVert\vec b\lVert} \dfrac{\vec b}{\lVert\vec b\lVert}
$$

말로 풀어보자. $\vec b$와 같은 방향성을 지니는 벡터를 $\vec a$와 $\vec b$ 간의 스칼라 프로젝션의 크기로 만들어주는 것이 벡터 프로젝션이다. 영상을 화면 위로 쏘는 행위를 떠올려보자. 이때 스크린에 해당하는 것이 $\vec b$이고 여기에 투영되는 상이 $\vec a$이다. 

### Projection as outer product 

$x$축 위로 프로젝션을 생각해보자. 이 역시 선형 변환이다. 기저를 생각하면 아래와 같다. 

$$
\Pi_{x}(
\begin{bmatrix}
1 \\
0 \\
\end{bmatrix}) = 
\begin{bmatrix}
1 \\
0 \\
\end{bmatrix}, ~
\Pi_{x}(
\begin{bmatrix}
0 \\
1 \\
\end{bmatrix}) = 
\begin{bmatrix}
0 \\
0 \\
\end{bmatrix}
$$

$$
M_{\Pi_x} = 
\begin{bmatrix}
\Pi_{x}(
\begin{bmatrix}
1 \\
0 \\
\end{bmatrix}),~
\Pi_{x}(
\begin{bmatrix}
0 \\
1 \\
\end{bmatrix}) 
\end{bmatrix} = 
\begin{bmatrix}
1 & 0 \\
0 & 0
\end{bmatrix}
$$

$M_{\Pi_x}$를 외적의 관점에서 표현해보자. 

$$
\begin{aligned}
\Pi_{x}(\vec v) & = (\hat i \cdot \vec v) \hat i = \hat i (\hat i \cdot \vec v) = \hat i (\hat i^T \vec v) = (\hat i \hat i^T)\vec v \\
& = 
\begin{bmatrix}
1 & 0 \\
0 & 0
\end{bmatrix} \vec v = M_{\Pi_x} \vec v
\end{aligned}
$$

이 결과를 일반적인 벡터 $\vec b$에도 확장할 수 있다. $\vec b$로의 프로젝션을 구현하기 위해서는 표준화된 벡터 $\hat b$를 먼저 구해야 한다. 

$$
\hat b = \dfrac{\vec b}{\Vert b \Vert},~M_{\Pi_{\hat b}} \vec a = \hat b \hat b^T \vec a  
$$  

$\vec a$를 인풋 벡터로 이해하면 이를 $\vec b$의 프로젝션 위치로 옮기는 선형 변환이 $\Pi_{\hat b}$에 해당한다. 

## More Definition 

- $S \subseteq \mathbb R^n$: $S$는 벡터 부분공간이라고 하자. 
- $S^\perp$: $S$와 직교 벡터들의 집합이고 이 역시 벡터 부분공간이다. 
$$
S^\perp = \{ \vec w \in \mathbb R^n : \vec w \cdot S = 0 \} 
$$
- $\Pi_S$: 부분공간 $S$ 위로 프로젝션 
- $\Pi_{S^\perp}$: 부분공간 $S^\perp$ 위로 프로젝션

$\Pi_S$는 일종의 함수로서 다음과 같이 정의된다. 

$$
\Pi_S: \mathbb R^n \to S
$$

 $\vec x \in \mathbb R^n$의 어떤 벡터가 $\Pi_S$를 거치면 $S$에 속하지 않는 나머지 부분은 사라지게 된다. 즉, $S$라는 화면 위로 자신의 이미지를 투영한다고 보면 된다. 그래서 프로젝션이다. 

몇가지 특징은 다음과 같다. 

- If ${\vec v} \in S$, then $\Pi_S(\vec v) = \vec v$
- If $\vec w \in S^\perp$, then $\Pi_S(\vec w) = \vec 0$
- if $\vec u = \alpha \vec v + \beta \vec w$ where $\vec v \in S$, $\vec w \in S^{\perp}$, then $\Pi_S(\vec u) = \alpha \vec v$
- $\Pi_S(\vec v) (\Pi_S(\vec v) ) = \Pi_S(\vec v)$ (idempotent) 

### Projection onto line 

![enter image description here](https://github.com/anarinsk/lostineconomics-v2-1/blob/master/images/projection/vector_proj.png?raw=true){: style="margin: auto; display: block; border:1.5px solid #021a40;"}{: width="500"}

그림에서 $\vec u$의 $\vec v$로의 프로젝션은 앞서 살펴본 벡터 프로젝션이다. $\vec v$ 대신 $l$로 표기된 점에 유의하자. 

$$
l: \{ \vec v' \in \mathbb R^n \lvert \vec v' = \vec 0 + t \vec v, t \in \mathbb R \}
$$

$$
\Pi_l(\vec u) = \dfrac{\vec u \cdot \vec v}{\lVert\vec v\lVert^2} \vec v
$$

이제 여기서 $\Pi_{l^{\perp}}$를 구해보자. 

$$
\vec u = \Pi_{l} (\vec u) + \Pi_{l^{\perp}} (\vec u)
$$

잠시 생각해볼 것이 있다. 

- $\Pi_{l^{\perp}}(\vec u)$가 의미하는 것은 무엇일까? $\vec u$에서 $\Pi_{l}(\vec u)$와 직교하는 벡터 프로젝션이다. 그런데, 둘은 $\Pi_{l^{\perp}}(\vec u)$ 만난다. 따라서, 프로젝션의 결과는 $\Pi_{l^{\perp}}(\vec u)$ 위에 있게 된다.위 그림은 이를 나타낸다. 
- $\vec u$라는 벡터가 두 개의 직교하는 성분의 결합을 통해 표현될 수 있다는 것을 알 수 있다. $\vec u = \Pi_{l}(\vec u) + \Pi_{l^\perp}(\vec u)$

### Projection onto plane 

![enter image description here](https://github.com/anarinsk/lostineconomics-v2-1/blob/master/images/projection/vector_proj_2.png?raw=true){: style="margin: auto; display: block; border:1.5px solid #021a40;"}{: width="500"}

평면 위로의 프로젝션을 생각해보자. 기본적인 원리는 동일하다. 이에 앞서 평면을 벡터로 표현하는 방법에 대해 알아보자. 가장 편리한 방법은 노멀 벡터를 활용하는 것이다. 즉, 평면 위의 점 $\vec {p_0}$를 지나는 $P$는 다음과 같이 정의할 수 있다. 

$$
P = \{ \vec p \in \mathbb R^n : \vec n \cdot(\vec p - \vec p_0) = 0 \}
$$

여기서 노멀 벡터 $\vec n$은 프로젝션된 지점에서 평면과 직교하는 성분을 나타낸다. 3차원의 경우 노멜 벡터는 3차원 공간에서 해당 평면이 놓인 모습을 결정한다. 

$$
\vec u = \Pi_P(\vec u) + \Pi_{P^\perp}(\vec u)
$$

그림에서 보듯이 $\vec u$에서 $\vec n$으로의 프로젝션은 앞서 보았던 벡터에서 벡터로의 프로젝션이다. 따라서 앞서 구한 공식을 그대로 활용하자.  즉,  

$$
\Pi_{P^\perp}(\vec u) = \dfrac{\vec u \cdot \vec n}{\lVert\vec n\lVert}\dfrac{\vec n}{\lVert \vec n \lVert}
$$

![enter image description here](https://github.com/anarinsk/lostineconomics-v2-1/blob/master/images/projection/vector_proj_2a.png?raw=true){: style="margin: auto; display: block; border:1.5px solid #021a40;"}{: width="500"}

벡터는 점과 달리 상대적인 위치로 정의된다. 벡터 연산은 그런 맥락에서 이루어진다. $\Pi_{P^\perp}$를 위 그림처럼 이동해 보자. 이렇게 보면 벡터 프로젝션이 자연스럽다. P에서의 위치는 변하지 않고 노멀 벡터 쪽으로만 변화하므로 벡터 자체는 이동 전 벡터와 이동 후 벡터가 동일하다. 즉,  $\Pi_{P^\perp}$를 왼쪽으로 이동시킨 벡터에 대한 프로젝션과 $\Pi_{P^\perp}$이 같다. 

$$
\Pi_{P^\perp} = \dfrac{\vec u \cdot \vec n}{\lVert\vec n\lVert^2}{\vec n}
$$

이제 $\Pi_{P^\perp}$ 대입하면 $\Pi_{P}$를 쉽게 구할 수 있다. 즉, 

$$
\Pi_P(\vec u) + \Pi_{P^\perp} = \vec u 
$$

$$
\Pi_P(\vec u)  = \vec u - \dfrac{\vec u \cdot \vec n}{\lVert\vec n\lVert^2}{\vec n}
$$

## Distance in Vector Space 

프로젝션은 거리를 측정할 때 유용하다. 먼저 원점(굳이 원점일 필요는 없다)과 해당 벡터 공간을 지나는 선 사이의 거리를 구해보자. 

$$
l: \{ \vec p \in \mathbb R^n | \vec p = \mathbf {p}_0 + t \vec v, t \in \mathbb R \}
$$

![enter image description here](https://github.com/anarinsk/lostineconomics-v2-1/blob/master/images/projection/line.png?raw=true){: style="margin: auto; display: block; border:1.5px solid #021a40;"}{: width="500"}

위 그림에서 원점과 $l$의 거리는 어떻게 나타낼 수 있을까? $l$이 지나가는 $\vec p_0$를 그대로 두고, $l$이 원점을 지나가도록 이동해보자. 즉, 

$$
l_0 = \{  \vec p \in \mathbb R^n | \vec p = \mathbf {0} + t \vec v, t \in \mathbb R \}
$$

![enter image description here](https://github.com/anarinsk/lostineconomics-v2-1/blob/master/images/projection/line_2.png?raw=true){: style="margin: auto; display: block; border:1.5px solid #021a40;"}{: width="500"}

이제 이 벡터과 $\vec p_0$ 사이의 거리를 구하면 된다 .이는 앞서 제시한 벡터 프로젝션의 수직 벡터의 길이와 같다. 즉, 

$$
d(l, \vec 0) = d(\vec p_0, l_0) = \lVert \mathbf p_0 - \dfrac{\mathbf p_0 \cdot \vec v}{\lVert \vec v\lVert^2}\vec v \lVert
$$

이제 아래와 같은 평면과 원점의 거리를 측정해보자. 

$$
P = \{ \vec p \in \mathbb R^n : \vec n \cdot(\vec p - \vec {p}_0) = 0 \}
$$

![enter image description here](https://github.com/anarinsk/lostineconomics-v2-1/blob/master/images/projection/plane.png?raw=true){: style="margin: auto; display: block; border:1.5px solid #021a40;"}{: width="500"}

원점을 지나도록 평면을 이동시키고 평면의 노멀 벡터가 정의된 $p_0$와 원점을 지나는 평면 $P_0$ 사이의 거리를 측정하면 된다. 

$$
P_0 = \{ \vec p \in \mathbb R^n : \vec n \cdot(\vec p - \vec {0}) = 0 \}
$$

이 둘 사이의 거리는 $\Pi_{P^\perp}$의 거리와 같다. 즉, 

$$
d(P, \vec 0) = d(P_0, \vec p_0) = \lVert  \dfrac{\vec p_0 \cdot \vec n}{\lVert\vec n\lVert}\dfrac{\vec n}{\lVert \vec n \lVert}\lVert = \dfrac{|\vec p_0 \cdot \vec n |}{\lVert\vec n\lVert}
$$

다시 확인해보자. 노멀 벡터 $\vec n$은 $\vec p_0$와 같은 같은 방향에 있는 벡터다. 따라서 위의 식이 성립한다. 

## Application: Regression Coefficient 

![enter image description here](https://github.com/anarinsk/lie-regression/blob/master/assets/imgs/reg-in-vectorspace.png?raw=true){: style="margin: auto; display: block; border:1.5px solid #021a40;"}{: width="500"}

앞서 소개했던 회귀 분석에 관한 포스팅 [Understanding Regression](https://anarinsk.github.io/lostineconomics-v2-1/math/econometrics/regression/2019/10/25/understanding-regression.html)을 다시 보자. Origin--Observed Y--Fitted $\hat Y$이 만드는 삼각형을 보자. 직각 삼각형이다. 여기서 잔차에 해당하는 $e$는 $X$의 컬럼 스페이스와 항상 직교한다. 즉, $X' e = 0$이 성립한다. 그리고 $\hat Y = X \hat\beta$이므로 

$$
X'(Y - \hat Y)  = X'(Y - X \hat\beta) = 0
$$

이를 노멀 방정식이라고 부른다. 앞서 평면과 직교하는 벡터를 노멀 벡터라고 불렀는데, 둘은 일맥상통한다.



## References 

- Ivan Savov, *No bullshit guide to linear algebra 2nd Edition*, Minireference, 2017 
  
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1ODc3NjU5MzMsMTIwNzg4MzkwNywxND
kxNTUxMzkxLC00MTI5NDc1ODksLTE4MDM2OTE2OTEsMTgwMzM1
NTM5NCwxMzk3MDg3NTcxLC0xMDc5MjIxMjU3LDIyODU3OTg1OS
wtMTU1MzE1Mzc2NSwyMzgzODczNjksLTMwODM5NTIyNywtMTY3
NjAyMzQzLDExNjIyNDgyMDcsMTUyMzEwMTc5NCwtNDY1MDM1ND
Y3LC0xMDkyODY4NTM2LDczODI1MzY4NSwtMjkyMzEyNTQ2LC0x
MjEyMzEwM119
-->
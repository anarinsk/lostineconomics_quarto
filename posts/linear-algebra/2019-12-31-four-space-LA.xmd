---
toc: true
layout: post
comments: true
title: Four Fundamental Spaces of Linear Algebra
description:  선형대수의 four horse men 
categories: [math, matrix-theory]

---


## Tales of Two Lines 

<p align="center"><kbd>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a3/Matrix_Rows.svg/510px-Matrix_Rows.svg.png" width="150">
   <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Matrix_Columns.svg/510px-Matrix_Columns.svg.png" width="150">
</kbd></p>

행렬을 행 공간(row space)으로 이해하는 것과 열 공간(column space)으로 이해하는 것은 같은 해를 구하는 문제에서도 전혀 다른 함의를 지닌다. 아래의 연립 방정식을 풀고 싶다고 하자. 

$$
\begin{aligned}
2 x + y & = 3\\
x - 2y & = -1
\end{aligned}
$$

행렬로 나타내면 다음과 같다. 

$$
\begin{bmatrix}
2 & 1 \\
1 & -2
\end{bmatrix}
\begin{bmatrix}
x \\
y
\end{bmatrix} = 
\begin{bmatrix}
3 \\
-1
\end{bmatrix} 
$$

### Row picture 

행으로 이해해보자. 이게 우리에게 익숙한 방식이다. 이 차원 평면($x$--$y$ 평면)에 직선 두 개를 그리고 교점을 찾으면 되겠다. 이것이 문제를 행으로 보는 관점이다. 아래 그림을 참고하자.[^1] 

[^1]: 그림의 출처는 [여기](https://www.youtube.com/watch?v=My5w4MXWBew)

<p align="center"><kbd>
  <img src="https://github.com/anarinsk/lie-4_spaces_LA/blob/master/assets/imgs/row-picture.png?raw=true" width="400">
</kbd></p>


### Column picture 

이제 이 문제를 컬럼으로 보자. 행렬을 열로 보면, $(2 \times 1)$ 벡터다. 이 벡터를 좌표로 나타나면 이제 $x$, $y$는 식의 방정식 우변의 벡터를 얻는 데 필요한 행렬의 두 행 벡터에 가중치가 된다. 아래 그림을 보자. 

<p align="center"><kbd>
  <img src="https://github.com/anarinsk/lie-4_spaces_LA/blob/master/assets/imgs/column-picture.png?raw=true" width="400">
</kbd></p>

### Which of two? 

둘 다 쓸모가 있는 관점이지만 열 공간으로 보는 관점이 몇 가지 점에서 수학적으로 좋다. 우선, 열 공간으로 보게 되면 계산에 동원되는 모든 대상들이 '벡터 공간'에 위치하게 된다. 벡터 공간은 반드시 $\boldsymbol{0}$을 포함해야 한다. 열 공간에서는 이게 가능하다. 투입과 산출이 모두 벡터로 표현되고 산출은 행렬을 구성하는 열 벡터의 선형 결합을 통해 표현된다. 이 선형 결합이 일종의 투입이 된다. 

그런데 행 공간의 관점에서는 벡터 공간의 수학적인 표현과 그 결과를 활용하기 힘들다. 2차원 벡터까지는 평면에 도해할 수 있지만 3차원도 보기에 부담스럽다. 

<p align="center"><kbd>
  <img src="https://github.com/anarinsk/lostineconomics-v2-1/blob/master/images/four-space/row_space.png?raw=true" width="400">
</kbd></p>

언감생심 $n(\geq 4)$ 차원을 도해하는 것은 불가능하다. 

물론 열 공간의 관점을 취한다고 해도 '정확한' 도해가 가능한 것은 아니다. 하지만 벡터 공간 안에서 정확하게 개념을 표시할 수는 있다. 아래 그림처럼 보통 벡터를 표현할 때 $\boldsymbol{0}$를 중심으로 벡터의 기호를 적는다. 적어도 그림상으로 벡터 스페이스 위에서 더하기와 곱하기를 표기하는 데 무리가 없다. 

<p align="center"><kbd>
  <img src="https://github.com/anarinsk/lostineconomics-v2-1/blob/master/images/four-space/column_space.png?raw=true" width="400">
</kbd></p>

확인 차원에서 열 공간의 관점에서 행렬을 '함수'로 이해하는 방식을 다시 살펴보자. 

$$
\underset{(m \times n)}{A} \underset{(n \times 1)}{x} = \underset{(m \times 1)}{b}
$$

이렇게 보면 행렬 $A$는 특정한 방식으로(선형의 방식으로) $x$를 차원이 다른 벡터 $b$로 변환한다.[^2] 이때 $A$의 경우 

[^2]: 함수로서의 행렬 $A$에 열 벡터 $x$를 투입했다고 하자. 산출은 행 벡터일까? 열 벡터일까? 열 벡터다.($1 \times 1$). k벡터가 나올 수는 있지만 열 벡터가 나온다. 이런 관점에서 이해하면 행렬 $A$의 우측에 열 벡터가 투입되면 열 벡터가 나오고, 좌측에 행 벡터가 투입되면 행 벡터가 나온다. 

$$
A = 
\begin{bmatrix}
\vert ~~ \dotsc ~~ \vert \\
c_1 ~\dotsc~ c_n \\
\vert ~~ \dotsc ~~ \vert 
\end{bmatrix},~\text{where}
$$

$$
c_i = 
\begin{bmatrix}
a_{1i} \\
\vdots \\
a_{mi}
\end{bmatrix}.
$$
이때, 투입 벡터 $x = [x_1, \dots, x_n]$는 열 벡터들, $c_i$를 조합해 $b$를 만들 수 있는 가중치를 찾는 문제가 된다. 

$$
A x = c_1 x_1 + c_2 x_2 + \dotsc + c_n x_n = b
$$

## Big Picture of Linear Algebra 

다시 강조하지만 기본적으로 행렬은 함수다. $A$는 투입 벡터 $x (\in {\mathbb R}^{n})$를 산출 벡터 $b(\in {\mathbb R}^{m})$로 바꾸는 역할을 한다. $A^T$는 투입벡터 $x^\prime \in {\mathbb R}^m$을 산출벡터 $b^\prime \in {\mathbb R}^n$으로 바꾼다. 이들 사이에 어떤 관계가 존재할까? 이를 나타내는 것이 길버트 스트랭(Gibert Strang) 선생이 말한 선형대수의 '큰 그림'이다. 아래 그림을 보자.  

<p align="center">
  <img src="https://github.com/anarinsk/lostineconomics-v2-1/blob/master/images/four-space/fundamental.png?raw=true" width="450">
</p>


그림 자체로 그냥 이해가 간다. 열 공간으로 이해하는 습관이 들었다면, 그림이 뒤집혀야 하지 않나, 싶겠지만 앞서 보았던 연립방정식처럼 $A x = b$의 형태로 이해하면 좋다.  

### Row space 

- $A$의 행 공간은 $\mathbb{R}^n$에 속한다. 

$$
A = 
\begin{bmatrix}
{\rm -} & r_1^T & {\rm -} \\
{\rm -} & \vdots & {\rm -} \\
& & \\
{\rm -} & r_m^T & {\rm -}
\end{bmatrix}
$$

- $r_i$는 $A$의 $i$ 번째 행을 원소로 하며,  $r_i \in {\mathbb R}^{n}$ 벡터다.  
- 행 공간의 영 공간(null space) 역시 $\mathbb{R}^n$에 속한다. 영 공간이란 $A x = \boldsymbol{0}$을 만족하는 $x \neq \boldsymbol{0}$의 벡터이므로 이 역시 $x \in {\mathbb R}^{n}$다. 

#### Orthogonality of row space and null space 

두 벡터는 직교할까? 행 공간 $\mathcal{R}$의 정의는 다음과 같다. 

$$
\mathcal{R}(A) = \{  x_r \in \mathbb{R}^n \vert x_r = \sum_{i=1}^{m}  \alpha_i  r_i,~\text{where}~ \alpha_i \in \mathbb{R}, ~r_i \in \mathbb{R}^n \}
$$

영공간(nullspace)에 속하는 벡터를 $x_n$라고 할 때(notation에 약간의 교란이 발생하지만 그림과의 일치를 위해 일단 이렇게 표기하도록 하자), 영공간의 정의에 따라서 $r_i^T x_n = 0$. 

$$
{x_r^T} x_n =  \sum_{i=1}^{m} \alpha_i (r_i^T x_n)  = 0
$$

그리고 그림에서 보듯이 다음과 같은 관계가 성립한다. 

- $A x_r = b_r (\in {\mathbb R}^m)$
- $A x_n = \boldsymbol{0}_m$
- $A (x_r + x_n) = b_r$
- $x_r^T x_n = 0$

위 관계에서 $b_r$, $\boldsymbol{0}$는 모두 열 공간에 존재하는 벡터들이므로 $(m \times 1)$의 크기를 지닌다는 점에 유의하자. 

#### Column space 

- $A$의 열 공간은 $\mathbb{R}^m$에 속한다.  

$$
\begin{bmatrix}
\vert ~~ \dotsc ~~ \vert \\
c_1 ~\dotsc~ c_n \\
\vert ~~ \dotsc ~~ \vert 
\end{bmatrix}, ~\text{where}~ c_i = 
\begin{bmatrix}
c_{1i}\\
\vdots \\
c_{mi} 
\end{bmatrix}.
$$

- 열 공간의 영 공간, 좌 영공간(left nullspace) 역시 $\mathbb{R}^m$에 속한다. 이는 $A^T x = 0$에 의해 정의된다. 
 
#### Orthogonality of column space and left null space 

- 나머지 과정은 비슷하게 전개할 수 있다. 열 공간 $\mathcal{C}$의 정의는 다음과 같다. 

$$
\mathcal{C}(A) = \{  x_c \in \mathbb{R}^m \vert x_c = \sum_{i=1}^{n} \alpha_i c_i,~\text{where}~ \alpha_i \in \mathbb{R}, ~c_i \in \mathbb{R}^m \}
$$

좌 영공간의 정의에 따르면, $c_i^T x_n = 0$가 성립한다. 따라서, 

$$
{x_c^T} x_n =  \sum_{i=1}^{n} \alpha_i (r_i^T x_n)  = 0
$$

- $A^T x_c = b_c(\in {\mathbb R}^n)$
- $A^T x_n = \boldsymbol{0}_n$
- $A (x_c + x_n) = b_r$
- $x_c^T x_n = 0$

### Exchange of row and column 

$A^T$의 열 공간이 곧 $A$의 행 공간이 된다. 따라서 $\mathcal{R}(A) = \mathcal{C}(A^T)$가 된다.
 
$$
A^T =  
\begin{bmatrix}
r_1 ~,\dotsc, ~ r_m
\end{bmatrix} 
$$

위의 그림을 컬럼 스페이스로만 다시 표현하면 다음과 같다. 즉, $A$의 행 공간은 $A^T$의 열 공간이다. 

<p align="center"><kbd>
  <img src="https://github.com/anarinsk/lie-4_spaces_LA/blob/master/assets/imgs/fundamental.png?raw=true" width="400">
</kbd></p>

### A simple example 

간단한 예 하나를 들어보자. 

$$
Ax = 
\begin{bmatrix}
1 \\
4 \\
1 \\
1
\end{bmatrix}.
$$

그리고 

$$
x=
\underbrace{
\begin{bmatrix}
0 \\
1 \\
1
\end{bmatrix} }_{x_p}+ 
c
\underbrace{
\begin{bmatrix}
0 \\
2 \\
1
\end{bmatrix}}_{x_s}, \forall c \in \mathbb{R}
$$

이 문제를 풀어보자. 우선 $A$을 열 벡터($c_i$)의 관점에서 바라보자. 

$$
A = 
\begin{bmatrix}
c_1, c_2, c_3
\end{bmatrix}
$$

$$
\begin{aligned}
Ax = c_2 + c_3 + c(2 c_2 + c_3) = 
\begin{bmatrix}
1 \\
4 \\
1 \\
1
\end{bmatrix}.
\end{aligned}
$$

모든 $c$에 관해서 성립해야 하므로, $2c_2 + c_3 = 0$은 항상 성립해야 한다. 따라서 

$$
A = 
\begin{bmatrix}
c_1, c_2, -2c_2
\end{bmatrix}.
$$

이제 행렬 $A$의 영 공간을 생각해보자. 영 공간이란 $A x = 0$을 만족하는 $x$로 이루어진 벡터 공간이다. $c$에 관계없이 $Ax = 0$을 만족해야 한다. 즉, 

$$
A x_s = [c_1, c_2, -2c_2] 
\begin{bmatrix}
x_1 \\
x_2 \\
x_3 \\
\end{bmatrix} = 
c_1 x_1 + c_2 x_2 - 2 c_2 x_3 = c_1 x_1 +c_2(x_2 - 2x_3) = 0
$$

이 해는 $x_1 = 0$, $x_2 = 2 x_3$가 영 공간에 존재하는 벡터이고 이것이 유일하다. 이를 만족하는 해는 $x$ 하나 밖에 없다. 즉, 

$$
x_{\rm null} = x_3
\begin{bmatrix}
0 \\
2 \\
1 \\
\end{bmatrix}.
$$


이제 앞서 본 4개의 근본 공간의 원리에 따라서 $A^T \in {\mathbb R}^{3 \times 4}$이고, $A^T$는 열 벡터 $a_i(\in {\mathbb R}^3)$로 구성된다. 따라서 $A^T$의 위수는 $3-1 = 2$가 된다. 그리고 $A^T$의 위수와 $A$의 위수는 같기 때문에 $A$의 위수 역시 2이다. 

## Why? 

이 네 개의 스페이스가 맺고 있는 관련성은 그 자체만으로도 중요하고 흥미로운 것이지만, 이를 통해 이른바 SVD(Singluar Value Decomposition)을 달성할 수 있다. 만일 위에서 보듯이 $A$의 열 공간과 $A^T$의 열 공간이 같은 위수를 지니지 않는다면 이런 분해는 불가능하다. 

<p align="center"><kbd>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c8/Singular_value_decomposition_visualisation.svg/1920px-Singular_value_decomposition_visualisation.svg.png" width="350">
</kbd></p>

먼저 매트릭스 $A$의 열 공간에 속하는 원소 중에서 $r$ 개만 서로 독립이라고 하자. 이렇다면 이 성분으로만 구성된 매트릭스 $U$를 만들 수 있다. 매트릭스 $U$의 켤레 전치행렬을 $U^*$라고 하면,  다음의 식이 성립한다. 

$$
U U^{*} = I_m
$$ 

그리고, 행 공간에 속하는 원소 역시 $r$ 개만 독립이고, 이를 기반으로 $V$를 만들 수 있다. 그리고 이 사이에 특성값(singular value)을 대각행렬로 지니는 $\Sigma$를 넣으면 $A$는 다음과 같이 세 가지로 분해된다. 

<p align="center"><kbd>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bb/Singular-Value-Decomposition.svg/1920px-Singular-Value-Decomposition.svg.png" width="350">
</kbd></p>

기본적으로 행렬은 함수다. 즉 어떤 벡터의 변형이다. $M$에 투입되는 $(n \times 1)$의 벡터 $x$가 있다고 하자.  

1. 벡터의 방향을 돌린다 ($V^*$). 
2. 특성값 행렬($\Sigma$)로 차원을 바꾸면서 좌표축의 크기를 조정한다.  
3. 마지막으로 $U$를 통해서 벡터의 방향을 돌린다. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI5MTMwNTEzLDYwOTc5MDE5NCwtMTQxMD
AzMzkyNiwzMjIyNDAzMjAsLTU4NDA0NDQwMywxMDIzNTcwMjcz
LDc0NTI1Nzk3MywxMjE0MjE5NTE0LDE2Njk3NTY2NTYsMTE2Mj
MwMTY5MCwtNzEyNTA5NTM4LDQ5OTcxNDEyMywtMTgwNDExNzUw
Ml19
-->
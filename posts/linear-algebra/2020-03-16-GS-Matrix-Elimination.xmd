---
layout: post
toc: false
comments: true
title: Following Gilbert Strang 1
description: 매트릭스 바라보는 법 그리고 소거법
categories: [math, matrix-theory, gilbert-strang]

---

## What 

- 선형 대수의 대 마왕 길버트 스트랭 님의 강의를 틈틈이 다시 듣고 있다. 
- 개인적으로 정리하는 내용이므로 많이 불친절하니 알아서들 보시라. 마. 
	- 스트랭 선생님의 원래 강의 취지와 다른 경우도 종종 있을 것이다... 

## Source 

[2. Elimination with Matrices](https://www.youtube.com/watch?v=QVKj3LADCnA)

## How To View Matrix

- 일단 매트릭스를 이해하는 방법부터 뜯어 고치자. 
- 계속 강조하듯이, 매트릭스는 일종의 함수다. 
	- 그런데 인풋을 왼쪽에도 넣을 수 있고, 오른쪽에도 넣을 수 있다. 

## Right Operation 

$A \in {\mathbb R}^{m \times n}$, $x \in {\mathbb R}^{n \times 1}$

$$
A x = 
\begin{bmatrix}
c_1 & \dotsc & c_n
\end{bmatrix}
\begin{bmatrix}
x_1 \\
\vdots \\
x_n
\end{bmatrix} = 
c_1 x_1 + \dotsb + c_n  x_n
$$

이 표기식은 $A$의 컬럼 벡터가 $x$의 원소들에 의해 선형결합되는 것임을 잘 보여준다. 

## Left Operation 

$A \in {\mathbb R}^{m \times n}$, $x \in {\mathbb R}^{1 \times m}$

$$
x A  = 
\begin{bmatrix}
x_1 & \dotsc & x_m
\end{bmatrix}
\begin{bmatrix}
r_1 \\
\vdots \\
r_m
\end{bmatrix} = 
x_1 r_1 + \dotsb + x_m  r_m
$$

이 표기식은 $A$의 로우 벡터가 $x$의 원소들에 의해 선형결합된다는 것을 보여준다. 

## Matrix Operation 

일단 이해를 돕기 위해서 $3 \times 3$ 매트릭스를 예로 들겠다. 

$$
T
\underbrace{\begin{bmatrix}
1 & 2 & 1 \\
3 & 8 & 1 \\
0 & 4 & 1 \\
\end{bmatrix}}_{A} = 
\underbrace{\begin{bmatrix}
1 & 2 & 1 \\
0 & 2 & -2 \\
0 & 4 & 1 \\
\end{bmatrix}}_{B}
$$

이때 변형 매트릭스 $T$를 어떻게 찾을 수 있을까? 먼저 $T$는 매트릭스 $A$의 왼쪽에 있다. 따라서 매트릭스 $T$의 로우 벡터들은 각기 $A$의 로우 오퍼레이션을 수행한다. 즉, 매트릭스 $B$의 첫번째 로우는 $A$와 같다. 따라서, $A$의 첫번째 행에는 $[1~0~0]$이 들어간다. 같은 논리로 $T$ 를 찾으면 다음과 같다. 

$$
T = 
\begin{bmatrix}
1 & 0 & 0 \\
-3 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

$T$는 무엇을 의미하는가? $B$의 경우 첫번째 로우와 세번째 로우는 $A$와 동일하다. 그리고 두번째 로우의 경우 첫번째 로우에 $-3$을 곱한 후 이를 두 번째 로우와 더한 것이다. 식은 이를 그대로 나타낸다. $T$의 경우 1열과 2열만 결합된다는 의미에서 $E_{12}$로 표기하기도 한다. 

그리고 이는 사실 사다리꼴 행렬 혹은 기약 사다리꼴 행렬을 만드는 과정이다. 자세한 것은 [이 포스트](https://anarinsk.github.io/lostineconomics-v2-1/math/matrix-theory/2020/01/07/Gauss-Jordan.html)를 참고하라. 

## Permutation matrix 

만일 $2 \times 2$ 매트릭스에서 1행과 2행을 바꾸는 작업은 어떻게 수행할까? 

$$
\begin{bmatrix}
0 & 1  \\
1 & 0 \\
\end{bmatrix}
\begin{bmatrix}
a & b  \\
c & d \\
\end{bmatrix} = 
\begin{bmatrix}
c & d  \\
a & b \\
\end{bmatrix}
$$

이렇게 하면 된다. 만일 1열과 2열을 바꾸고 싶다면? 열을 조작하는 작업이니 이번에는 매트릭스가 $A$의 오른쪽에 와야 한다. 

$$
\begin{bmatrix}
a & b  \\
c & d \\
\end{bmatrix}
\begin{bmatrix}
0 & 1  \\
1 & 0 \\
\end{bmatrix} = 
\begin{bmatrix}
b & a  \\
d & b \\
\end{bmatrix}
$$

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU5NzgyNDQ1LDE3NTQ0NTgyOTAsMTI5Mj
g0OTA5NV19
-->
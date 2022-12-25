---
toc: true
layout: post
comments: true
title: Matrix Decomposition 
description: 행렬 분해를 한 방에 정리해보자 
categories: [math, matrix-theory]

---

## Summary in advance 

|Name| $A \in$  | Restriction | Comments |
|--|--|--|--|
| LU | ${\mathbb R}^{m \times n}$ | | 
| Cholesky | ${\mathbb C}^{n \times n}$ | PD, Symmetric(Hermite) | fast algorithm |
| Eigendecomposition |  ${\mathbb C}^{n \times n}$ | invertible |
| QR | ${\mathbb R}^{m \times n}$| |Gram-Schmidt processing |
| SVD |  ${\mathbb C}^{m \times n}$ | | |

- $m \geq n$

## LU Decomposition

- $A \in {\mathbb R}^{n \times n}$
기본적으로는 [가우스-조르단 소거법](https://anarinsk.github.io/lostineconomics-v2-1/math/matrix-theory/2020/01/07/Gauss-Jordan.html)을 떠올리면 좋다. 가우스 소거법이란게 뭔가? 우리가 중고등학교 때 배웠던 연립방정식의 해를 얻는 과정이다. LU 방법은 가우스-조르단 소거법은 2단계로 분리한 형태라고 이해하면 된다. 

### Row operation

- **Row exchange** 
	- 연립방정식을 풀 때 식의 순서를 바꾼다고 해가 달라지지는 않는다. 
- **Multiply a row by a nonzero constant** 
	- 어떤 식의 양변에 0이 아닌 수를 곱한다고해서 해가 달라지지는 않는다. 
- **Add one row to another** 
	- 연립방정식의 해를 구하는 과정이 이러한 식 조작의 연속이다. 

### Solution for linear equation 

$A x = b$와 같은 적당한 선형 연립방정식이 있다고 하자. 이때 

$$
P A= LU 
$$

- P는 행과 열을 적당히 재배치하는 데 동원되는 순열 행렬이며, 0과 1만 원소로 지닌다.[^2]

[^2]: $P$가 왜 필요한지 생각해본 적이 있는가? 보통 대수적인 관점에서 보면 $A=LU$로 충분하다. 하지만 계산의 관점에서 보자. 피봇 원소가 지나치게 작으면 계산이 성가시다. 얘네들은 뒤로 미뤄놓고 0으로 간주하면 계산이 쉽지 않겠는가? 따라서 계산의 관점에서 보면 $P$를 통해 $A$의 피봇을 큰 순서대로 정렬하는 것이 좋다. 

$$
\begin{aligned}
P A x & = P b \\
LU x & = Pb
\end{aligned}
$$

이때, $Ux =y$라고 두고 문제를 한번 풀고, $Ly = Pb$라고 두고 문제를 다시 한번 풀면 해를 쉽게 구할 수 있다. 

### Determinant 

$A = P^{-1} L U$ 를 만족하고, 

$$
\begin{aligned}
\det A & = \det P^{-1} \det L \det U \\
& = \det P (\prod _{i=1}^{n} l_{ii}) (\prod _{i=1}^{n} u_{ii}) \\
& = (-1)^S (\prod _{i=1}^{n} l_{ii}) (\prod _{i=1}^{n} u_{ii})
\end{aligned}
$$

- $S$는 행이 교환된 횟수를 나타낸다. 
- $P$는 직교행렬이므로, $P^{-1} = P^T$가 성립한다. 
- UTM(Upper Triangular Matrix, 상삼각 행렬), LTM(Lower Triangular Matrix, 하삼각 행렬)의 경우 행렬식의 값은 대각원소를 곱한 것과 같다. 

## Cholesky Decomposition 

- $A  \in {\mathbb C}^{n \times n}$
- 에르미트 행렬(Hermite matrix)이란 $A$가 그 켤레 전치(conjugate transpose) 행렬($A^*$)과 같은 행렬이다. 

$$
A = A^*,~\text{where}~A_{ij} = \overline{A_{ji}}
$$
- 이때 에르미트 행렬이고 양정부호 행렬 $A$가 있을 때 숄레스키 분해는 다음과 같다. 

$$
A = L L^*
$$

- $L$은 LTM이며, $L^*$는 UTM이다. 한편 $L$의 대각성분은 모두 양의 실수가 된다. 
- 만일 $A \in {\mathbb R}^{n \times n}$이라면, 

$$
A = L L^T
$$

- LU 분해의 특별한 경우라고 볼 수 있다. 알고리듬의 관점에서보면, LU에 비해 숄레스키 분해가 2~3 배 빠르다. 

## Eigendecomposition 

- $A \in {\mathbb R}^{n \times n}$
- 자세한 내용은 [여기](https://anarinsk.github.io/lostineconomics-v2-1/math/matrix-theory/2019/12/03/eigenvalue-eigenvector.html)를 참고하면 된다. 
- 행렬 $A$가 가역일 경우 $A = Q \boldsymbol{\lambda}Q^{-1}$로 분해할 수 있다. 
- 만일 $A$가 가역이고 대칭행렬이라면, $Q^T Q = I$ 이므로 $Q^{-1} = Q^T$가 된다. 따라서 $A = Q \boldsymbol{\lambda}Q^{T}$

## QR decomposition 

- $A \in {\mathbb R}^{n \times n}$
- 행렬을 직교 행렬과 삼각 형렬(UTM, LTM)로 분해하는 과정을 뜻한다. 

### Gram-Schmidt processing 

$$
A = 
\begin{bmatrix}
\vert ~ & \dotsc & ~ \vert \\
v_1 ~ & \dotsc & ~ v_n \\
 \vert ~ & \dotsc & ~ \vert \\
\end{bmatrix}
$$

$$
\begin{aligned}
u_1 = v_1, & ~e_1 = \dfrac{u_1}{\Vert u_1 \Vert} \\
u_2 = v_2 - (v_2 \cdot e_1) e_1, &~e_2 = \dfrac{u_2}{\Vert u_2 \Vert} \\
v_{k+1} = v_{k+1} - (v_{k+1} \cdot e_1) e_1 - \dotsb-(v_{k+1} \cdot e_k)e_k,&~e_{k+1} = \dfrac{u_{k+1}}{\Vert u_{k+1} \Vert}
\end{aligned}
$$

<p align="center"><kbd>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/97/Gram%E2%80%93Schmidt_process.svg/1200px-Gram%E2%80%93Schmidt_process.svg.png" width="400">
</kbd></p>

- G-S 과정은 위 그림이 잘 표현해준다. 즉, 그림의 $v_2$(식의 $a_2$)에서 $e_1$으로 프로젝션을 한 벡터를 빼주게 되면 $v_1$과 직교하는 $u_2$를 얻을 수 있는 것이다. 

- 과정을 행렬의 곱으로 재배열해준 것이 QR 분해다. 즉, 

$$
\begin{aligned}
A & = \begin{bmatrix}
\vert ~ & \dotsc & ~ \vert \\
v_1 ~ & \dotsc & ~ v_n \\
 \vert ~ & \dotsc & ~ \vert \\
\end{bmatrix} \\
& =\underbrace{ [e_1 ~ \dotsc ~ e_n] }_{Q}
\underbrace{
\begin{bmatrix}
v_1 \cdot e_1 & v_2 \cdot e_1 & \dotsc & v_n \cdot e_1 \\
0 &  v_2 \cdot e_2 & \dotsc  & v_n \cdot e_2 \\
\vdots &  \vdots & \ddots  & \vdots \\
0 &  0 & \dotsc  & v_n \cdot e_n \\
\end{bmatrix}}_{R}
\end{aligned}
$$

- $e_1, \dotsc, e_n$만 구하면 쉽게 분해를 달성할 수 있음을 알 수 있다. 그리고 이렇게 분해가 가능한 이유는 G-S 알고리듬 때문이다. 

### Least quares solution 

- QR 분해는 다소 엉뚱하게도 최소자승법의 해를 구할 때 유용하게 활용할 수 있다. 

먼저 $A \in {\mathbb R}^{m \times n}$ ($m \geq n$)이라고 하자. 이때 다음과 같은 QR 분해가 존재하다. 

$$
A = Q 
\begin{bmatrix}
R \\
0
\end{bmatrix}
$$

- $Q \in {\mathbb R}^{n \times n}$의 직교행렬(즉, $Q^{-1} =Q^T$), $R \in {\mathbb R}^{m \times m}$의 UTM(upper triangular matrix, 상삼각행렬)이다. 
- 만일 $m = n$이고 $A$가 가역이면 QR 분해는 유일하다. 
- 이제 $A$가 full-column rank(즉, ${\rm rank}(A) = n$)라고 하면, A의 QR 분해는 아래와 같이 쓸 수 있다. 

$$
A = [Q_1, Q_2] 
\begin{bmatrix}
R \\
0
\end{bmatrix} = Q_1 R 
$$

이제 최소자승법의 목적함수를 다음과 같이 써보자. 

$$
\begin{aligned}
\Vert A x - b \Vert^2_2 & = \Vert Q^T(Ax-b) \Vert \\
& = \Vert 
\begin{bmatrix}
R \\
0
\end{bmatrix}  x - Q^T b \Vert  \\
& = \underbrace{\Vert Rx - d_1 \Vert}_{(\ast)} + \Vert d_2 \Vert
\end{aligned}
$$

이때 $\Vert d_2 \Vert$는 상수이므로, 극소화 문제는 $(\ast)$를 최소화하면 된다. 그리고 저 거리를 최소화해주는 것은 당연하게 

$$
x = R^{-1} d_1 
$$

- 이 해는 normal equation을 최소화하여 얻은 해와 같음을 알 수 있다. 

## Singular Value Decomposition 

- $M \in \mathbb{C}^{m \times n}$ 

$$
M = U \boldsymbol{\Sigma} V^*
$$

- eigendecomposition를 보다 일반화했다고 보면 좋겠다. 
- $U \in \mathbb{C}^{m \times  m}$: 유니터리 행렬, 즉 $U U^* = I_m$
- $\boldsymbol{\Sigma \in \mathbb{R}^{m \times  n}}$: 대각 원소가 음수가 아니며 나머지 원소는 모두 0
- $V^* \in \mathbb{C}^{n \times  n}$: 유니터리 행렬, 즉 $V V^* = I_n$
- 만일 $U$, $V$가 모두 실수라면 각각은 $m$ 차원 $n$ 차원의 직교 행렬이다. 

### Geometric interpretation 

<p align="center"><kbd>
  <img src="https://github.com/anarinsk/lie-matrix_decomp/blob/master/assets/imgs/SVD.png?raw=true" width="450">
</kbd></p>

기하학적으로 해석해볼 수 있겠다. 대체로 유니터리 혹은 직교 행렬들을 서로 직교하는 축을 회전하는 역할을 한다. 한편, 실수로 구성된 대각 행렬을 벡터의 길이를 늘이고 줄이는 역할을 한다. 아울러 SVD에서는 차원을 조정하는 역할을 한다. 어떤 축은 없애기도 하고, 없던 축을 생성하기도 한다. 

따라서 어떤 $x \in {\mathbb C}^{n \times 1}$가 있을 때 

- $V^*$는 이 벡터의 축을 바꿔준다. 
- $\boldsymbol{\Sigma}$은 각 축의 단위 거리와 차원을 조정한다. - $U$는 다시 벡터의 축을 바꾼다. 

### Reduced SVD 

- SVD를 도식화해서 나타내면 아래와 같다. 

<p align="center"><kbd>
  <img src="https://github.com/anarinsk/lie-matrix_decomp/blob/master/assets/imgs/svd1.png?raw=true" width="450">
</kbd></p>

- 그리고 관례상 $\boldsymbol{\Sigma}$은 큰 순서대로 나열하는 것으로 한다. 

#### Thin SVD 

<p align="center"><kbd>
  <img src="https://github.com/anarinsk/lie-matrix_decomp/blob/master/assets/imgs/svd2.png?raw=true" width="450">
</kbd></p>

- svd가 존재하지 않은 영역은 사실상 불필요한 셈이니 이들을 잘라낸다. 

#### Compact SVD

<p align="center"><kbd>
  <img src="https://github.com/anarinsk/lie-matrix_decomp/blob/master/assets/imgs/svd3.png?raw=true" width="450">
</kbd></p>

- 만일 svd가 0인 값들이 들어 있다면, 이들을 제외하고 다시 비슷한 축약을 거친다. $r < s$

#### Truncated SVD 

<p align="center"><kbd>
  <img src="https://github.com/anarinsk/lie-matrix_decomp/blob/master/assets/imgs/svd4.png?raw=true" width="450">
</kbd></p>

- svd 값을 일정한 기준으로 잘라낸 것이다. 즉, 해당 기준 이후의 값들을 쳐냈다고 보면 좋다. 

이때, raw, thin, compact는 정보의 손실이 없다는 점을 상기하자. Truncated 부터 정보의 손실이 발생한다.[^1] 
[^1]: 이런 특성 때문에 truncated SVD는 이미지 압축에 많이 활용된다. [여기](https://darkpgmr.tistory.com/106)에서 그 사례를 확인할 수 있다. 

### Pseudo-inverse 

보통 $A \in {\mathbb R}^{m \times n}$ ($m > n$)인 경우 역행렬을 구할 수 없다. 이때 역행렬과 최대한 비슷한 행렬을 찾는 것이 목표다. 만일 $Ax = b$에서 역행렬이 존재한다면 $x = A^{-1}b$로 쉽게 구할 수 있다. 하지만 역행렬이 존재하지 않는다면 어떤 $x$를 구하는 게 좋을까?  $\Vert  Ax - b \Vert$를 최소화하는 $x$를 구한다고 할 때, 이를 달성해주는 $A^+$를 $A$의 유사역행렬이라고 부른다. 즉, 

$$
x = A^+ b
$$

SVD는 이 유사역행렬을 구하는 과정에서 활용될 수 있다. 즉, $A =  U \boldsymbol{\Sigma} V^*$이라면 $A^+ =  V \boldsymbol{\Sigma}^+ U^*$라고 둘 수 있다. 여기서 

- $\boldsymbol{\Sigma}^+$는 $\boldsymbol{\Sigma}$의 대각 원소 중 0이 아닌 것들의 역수를 넣은 후 이를 전치한 행렬을 뜻한다. 즉, 

$$
A = \underbrace{U}_{m \times m}
\underbrace{
\begin{bmatrix}
\sigma_1 ~\dotsb~ 0 \\
\vdots ~ \ddots ~ \vdots \\
0 ~\dotsb ~ \sigma_s \\
0 ~~\dotsb ~~ 0 \\
\vdots ~ \ddots ~ \vdots \\
0 ~~\dotsb ~~ 0 \\
\end{bmatrix}
}_{m \times n}
\underbrace{V^T}_{n \times n}
$$

$$
A^+ = \underbrace{V}_{n \times n}
\underbrace{
\begin{bmatrix}
\frac{1}{\sigma_1} ~\dotsb~ 0~0 ~ \dotsb ~ 0\\
\vdots ~~ \ddots ~~ \vdots ~~ 0 ~ \dotsb ~ 0 \\
0 ~\dotsb ~ \frac{1}{\sigma_s} ~ 0 ~ \dotsb ~ 0 \\
\end{bmatrix}
}_{n \times m}
\underbrace{U^T}_{m \times m}
$$

- 이는 사실 최소자승법과 같은 해를 구해준다. 
- $A^{-1}$은 행렬의 좌곱과 우곱이 동일한 단위 행렬을 생성한다. 반면, 

$$
A^+ A = ( V \boldsymbol{\Sigma}^+ U^T)  (U \boldsymbol{\Sigma} V^T) = V V^T = I_n 
$$

$$
AA^+ =  (U \boldsymbol{\Sigma} V^T) ( V \boldsymbol{\Sigma}^+ U^T) = U U^T = I_m 
$$


## Sources 

[https://darkpgmr.tistory.com/106](https://darkpgmr.tistory.com/106)


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyODgxMDI5NjUsLTc0OTc3MjU5MSwxNj
IxNTM4ODUyXX0=
-->
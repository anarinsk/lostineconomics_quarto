---
layout: post
toc: false
comments: true
title:  Eigenspace, part 2
description: 아이겐 공간을 이해하자.  
categories: [math, matrix-theory]
---

## Singluar Value Decomposition

$A \in \mathbb C^{m \times n}$을 생각해보자. 이런 조건에서 아이겐 분해를 어떻게 활용할 수 있을까? 일단 $A$를 정방행렬로 만들어주어야 할 것이고, 이에는 두 가지 방법이 있다. 

$$
\underbrace{A^T A}_{n \times n}, \overbrace{A A^T}^{m \times m}
$$

아울러, $(A^T A)^T = A^T A$, $(AA^T)^T = A A^T$가 성립하기 때문에 두 매트릭스 모두 normal 매트릭스다. 따라서 아래와 같은 개념화가 가능하다. 

$$
A = 
\underbrace{
\begin{bmatrix}
\vert & \dotsb & \vert \\
u_1 & \dotsb & u_m \\
\vert & \dotsb & \vert \\
\end{bmatrix}}_{m \times m}
\overbrace{
\begin{bmatrix}
\sigma_1 & 0 & \dotsb \\
0 & \sigma_2 & \dotsb \\
0 & 0 & \dotsb \\
\end{bmatrix}}^{m \times n}
\underbrace{
\begin{bmatrix}
-- & v_1^T & -- \\
-- & \vdots & -- \\
-- & v_n^T & -- \\
\end{bmatrix}}_{n \times n} =
U \Sigma V^T
$$

$U$를 통해 분해되는 부분을과 $V$를 통해 분해되는 부분을 다음과 같이 나타내보자. 

$$
\begin{aligned}
A A^T & = U \Lambda_l U^T \\
A^T A & = V \Lambda_r V^T \\
\end{aligned}
$$

소문자의 $l$와 $r$은 각각 left, right를 뜻한다. $U$와 $V^T$를 명시적으로 적어보자. 


$$
U = 
\begin{bmatrix}
\vert & \dotsb & \vert \\
u_1 & \dotsb & u_m \\
\vert & \dotsb & \vert \\
\end{bmatrix}, \text{~where}
\{ (\lambda_i, u_i) = \text{eigenvects}(A A^T) \}
$$

$$
V = 
\begin{bmatrix}
-- & v_1^T & -- \\
-- & \vdots & -- \\
-- & v_n^T & -- \\
\end{bmatrix}, \text{~where}
\{ (\lambda_i, v_i) = \text{eigenvects}(A^T A) \}
$$

이제  유사 대각행렬 $\Sigma$를 보자. 이 행렬은 $m \times n$ 형태다. 

$$
\sigma_i = \sqrt{\lambda_i}, \text{ where } \lambda_i = \text{eigenvals}(A A^T) = \text{eigenvals}(A^T A) 
$$

### Change-of-basis 

기저를 바꾸는 관점에서 다시 음미해보자. 

$$
\vec y = A \vec x = U \Sigma V^T \vec x
$$

- $V^T \vec x$: $V^T = \phantom{}\_{B\_{SVD}}[1]\_{B_S}$. 즉, $B_{SVD} \leftarrow B_S$를 수행한다. 
- $\Sigma$: 유사 대각행렬을 곱해 각 기저의 크기를 조절한다. 
- $U$: $U = \phantom{}\_{B_{S}}[1]\_{B\_{SVD}}$: $B_{S} \leftarrow B_{SVD}$

즉, $B_S \leftarrow B_{SVD} \leftarrow B_S$를 수행한다. 

### Outer product 

외적의 관점에서 이해하는 것도 흥미롭다. 일단 외적에 관해서 간단히 살펴보자. 벡터 $u \in \mathbb R^m$, $v \in \mathbb R^n$이 있다고 할 때, 

$$
u v^T \in \mathbb R^{m \times n}
$$

외적의 rank는 어떻게 될까? 1이다. 직관적으로는 이해가 안될 수 있다. 

$$
{\rm rank} (AB) \leq \min({\rm rank}(A), {\rm rank} (B)) =  1
$$

SVD 식을 다시 조립해보자. 일단 $m \geq n$을 가정하자. 

$$
U \Sigma = 
\begin{bmatrix}
\vert & \dotsb & \vert \\
u_1 & \dotsb & u_m \\
\vert & \dotsb & \vert \\
\end{bmatrix}
\begin{bmatrix}
\sigma_1 & 0 & \dotsb \\
0 & \sigma_2 & \dotsb \\
0 & 0 & \dotsb \\
\end{bmatrix} 
$$

$$
\begin{aligned}
A & = U \Sigma V^T \\
& =
\underbrace{
\begin{bmatrix}
\sigma_1 u_1, \dotsb,  \sigma_n u_n, \dotsc,  0 u_m
\end{bmatrix}}_{U \Sigma}
\begin{bmatrix}
-- & v_1^T & -- \\
-- & \vdots & -- \\
-- & v_n^T & -- \\
\end{bmatrix} \\
& =  \sigma_1 u_1 v_1^T + \dotsb + \sigma_n u_n v_n^T + \dotsb + 0 u_m v_m^T
\end{aligned}
$$

$u_i v_i^T$는 각각 1의 rank를 지니고 앞에 곱해진 singular value의 기저로 이해할 수 있다. 해당 기저들의 선형 결합으로 매트릭스 $A$를 다시 분해할 수 있다. 

### An application 

이렇게 대각화를 할 때 어떤 이득이 있을까? 앞서 유사 행렬을 활용하면 행렬의 곱이 간단해진다는 점을 보았다. SVD에도 비슷한 이점이 있다. 이 외에 SVD를 써서 할 수 있는 중요한 이득이 있다. 계산량을 줄이는 것이다. 

$M \in \mathbb R^{1000 \times 2000}$의 변환이 있다고 하자. 이 변환의 싱귤러 밸류들 많아야 1000개가 나올 것이다. 만일 이 1000개 중에서 3개를 제외하고 나머지 값이 0에 가깝다고 하자.

$M$이라는 변환의 근사값을 구하고 싶다면, 0에 가까운 값을 모두 0으로 둔다. 이렇게 바꾸면, 

$$
M \approx \hat M = \hat U \hat \Sigma \hat V^T
$$ 

- $\hat U \in \mathbb R^{1000 \times 3}$ 
- $\hat \Sigma \in \mathbb R^{3 \times 3}$
- $\hat V^T \in \mathbb R^{3 \times 2000}$

이렇게 근사값을 구하면 계산량이 많이 줄어들 것이다. $M$와 $\hat M$ 사이의 힐베르트-슈미트 거리를 구하면, 

$$
\Vert M - \hat M \Vert_{\rm HS} = \sqrt{\sum_{i=4}^{1000} \sigma_i^2}
$$

이 값이 크지 않다면, $M \approx \hat M$으로 간주할 수 있다. 실제로 이미지 압축 등에서 많이 사용되는 방법이다. 

## LU 

$n \times n$ 정방 행렬에 대해서 $A = LU$를 수행할 수 있다. $L$과 $U$는 하방삼각 행렬과 상방삼각 행렬이다. 이렇게 매트릭스를 쪼개는 이유를 각각에 관해서 역행렬을 구하기 힘들기 때문이다. 즉, 

$$
A \vec x = LU \vec x = b \Leftrightarrow U \vec x = L^{-1}b \Leftrightarrow \vec x = U^{-1}L^{-1}b
$$

우선 LU가 가능하라면 $A$가 RREF으로 열의 교환 없이 환원될 수 있어야 한다. 

### Cholesky

$A$가 대칭이고 PSD 매트릭스라면 $LU$ 분해는 더욱 단순해진다. 

$$
A = L L^T \text{ or } A = U^T U 
$$
 
## QR 

$A \in \mathbb R^{n \times n}$일 때 이 매트릭스를 쪼개는 강력한 방법은 G-S 알고리듬을 활용하는 것이다. 

$$
A = O U 
$$

- $O$: orthogonal matrix 
- $U$: Upper triangluar matrix 

보통 $U$를 right-triangular matrix로도 쓰기 때문에, 이를 $QR$로 표기하기도 한다. $R$의 경우 $O$의 컬럼 벡터를 하나씩 추가해가면서 계산하게 된다. 이는 G-S 알고리듬에서 하나씩 벡터를 빼가면서 계산하는 것을 구현할 수 있게 해준다. 

### Example 

실제로는 어떻게 하는지 살펴보자. 먼저 $A$의 각 컬럼들을 두고, 두번째 열은 첫번째에 직교하게, 세번째는 첫번째와 두번째에 직교하게 행렬을 변형한다. 

$$
A = 
\begin{bmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33} 
\end{bmatrix}
$$

$O$ 혹은 $Q$를 구해보자. G-S 알고리듬을 활용하자. 

$$
A = [a_1, a_2, a_3]
$$

$a_1$과 직교하는 $e_2$를 구하면 아래와 같다. 

$$
e_2 = a_2 - \dfrac{a_2 \cdot a_1}{\Vert a_1 \Vert^2}
$$

다음으로 $e_3$는 $a_1$과 직교하고 동시에 $e_2$와 직교해야 한다. 따라서, 

$$
e_3 = a_3 - \dfrac{a_3 \cdot a_1}{\Vert a_1 \Vert^2} - \dfrac{a_3 \cdot e_2}{\Vert e_2 \Vert^2}
$$ 

이를 다시 길이 1로 표준화하면 $Q$를 구할 수 있다. 그리고 

$$
Q^T A = Q^T Q R = 1 R
$$

따라서 $R$은 $Q^T A$로 구할 수 있다. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzAzMDc4NjM4LDkyMzM2MDQ1NCwtOTE4OD
UxNjc4LC05NDMxMTE1MDUsMTM1MjA2MDIyLDE0NTI1NTY4MTAs
MTA2MTYwMTEzNywtMjEyNzA0NDgyOSwtMTYyMTY0ODM2OSw1OT
I4MDIwMDIsLTIwMjMzODg3NTAsMF19
-->
---

layout: post
toc: false
comments: true
title: Following Gilbert Strang 6
description: 네 개의 근본 벡터 스페이스  
categories: [math, matrix-theory, gilbert-strang]

---

## Oringinally 

[https://www.youtube.com/watch?v=nHlE7EgJFds](https://www.youtube.com/watch?v=nHlE7EgJFds)
[https://www.youtube.com/watch?v=2IdtqGM6KWU](https://www.youtube.com/watch?v=2IdtqGM6KWU)

## Basically 

<p align="center"><kbd>
  <img src="https://github.com/anarinsk/lie-4_spaces_LA/blob/master/assets/imgs/fundamental.png?raw=true" width="400">
</kbd></p>

- 기본적으로 위의 그림을 이해할 수 있으면 된다. 

### Column space 

매트릭스 $\mathbf A \in \mathbb R^{m \times n}$의 컬럼이 생성하는 공간을 나타낸다. $\mathbf A$의 컬럼 $c_i \in \mathbb R^{m}$이다. 

### Null space 

그냥 영 공간이라고 하면 컬럼 스페이스를 기준으로 나타낸다. 정의상 

$$
\mathbf A x = 0
$$

을 만족하는 $x$의 집합이다. 

- Null space임에 주의하자. 이 집합은 벡터 스페이스다! (따라서 무조건 $0$을 포함하고 있다) 
	- 참고로 $\mathbf A x = b (\neq 0)$를 만족하는 $x$, 즉 non-homogeneous system의 해가 형성하는 공간은 벡터 스페이스가 될 수 없다. 

- $x \in \mathbb R^n$임에 유의하자. 컬럼 스페이스에 짝을 이루는 널 스페이스는 그  차원이 동일하지 않다. 

- 로우 스페이스, 즉 $\mathbf A^T$의 컬럼 스페이스와 $\mathbf A$의 영 공간이 직교해야(orthogonal) 한다. 왜 그럴까? 

$$
\mathcal C (\mathbf A^T ) = \alpha_1 r_1 + \dotsb + \alpha_m r_m 
$$

where $r_i$ is $i$'th row vector of $\mathbf A$ (or $i$'th column vector of $\mathbf A^T$) and $a_i \in \mathbb R$. 

한편 컬럼 스페이스의 영 공간의 정의에 따라서 $\mathbf A x = 0$이 성립해야 한다. 즉,  

$$
\begin{bmatrix}
r_1 \\
\vdots \\
r_m
\end{bmatrix} x = 0
$$

즉, $r_i^T  x = 0$. 


이제 보여야하는 것은 

$$
(\alpha_1 r_1 + \dotsb + \alpha_m r_m)^T x = 0
$$

이는 자명하다. 

## Matrix Space 

- 벡터 스페이스처럼 매트릭스 스페이스라는 걸 생각해보자. 사실 벡터 스페이스에 '벡터'만 있는 것은 아니다. 벡터 스페이스란 addition와 scalar multiplication이 정의되는 공간을 의미한다. 
	- 벡터 서브 스페이스란? 벡터 스페이스의 부분집합이면서 마찬가지로 해당 부분집합 내에서 addition와 scalar multiplication이 성립하는 공간이다. 

### 3 X 3 Matrices 

- $3 \times 3$의 모든 매트릭스 $\mathbf M \in \mathbb R^{3 \times 3}$의 스페이스를 생각해보자. 
	- 이 공간은 벡터 스페이스인가? (new vector space) 
	- Addition and scalar multiplication

### Sysmmetric matrices and UTMs

- Are they vector space? YES 
- $r(S)$ and $r(U)$? 6 both 
- $S \cap U$? vector space and $r(S \cap U)=3$
- $S \cup U$? NO! 
- $S + U?$ 만일 $S$와 $U$가 연장된 개념이라면? 
	- 이는 사실 벡터 스페이스라는 개념이 나온 이유이기도 하다. 어떤 두 집합의 합집합 위에서는 연산이 정의되지 않거든. 

#### Basis for matrices 

$$
\begin{bmatrix}
1 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0 \\
\end{bmatrix}, 
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0 \\
\end{bmatrix}, \dotsc ,
\begin{bmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 1 \\
\end{bmatrix}
$$

## Rank One Matrix 

$$
\begin{bmatrix}
1 & 4 & 5 \\
2 & 8 & 10 
\end{bmatrix}
$$

- dim $\mathcal C(\mathbf A) =r (\mathbf A)$ = dim $\mathcal C(\mathbf A^T)$

$$
\begin{bmatrix}
1 \\ 2 \\
\end{bmatrix}
\begin{bmatrix}
1 & 4 & 5
\end{bmatrix}
$$

- rank one matrices can be represented by $\mathbb A = u v^T$

#### Examples 

In $\mathbb R^4$, 

$$ 
v = 
\begin{bmatrix}
v_1 \\
v_2 \\
v_3 \\
v_4 
\end{bmatrix}
$$

$S$ is all $v$ with $v_1 + v_2 + v_3 + v_4 = 0$

- $S$ is null space of $\mathbf A$? 
	- $\mathbf A = \begin{bmatrix} 1&1&1&1 \end{bmatrix}$
	- $r(\mathcal A) = 1$
	- dim $\mathcal N(A) = 4-1$  
- Basis for $S$
	- $\mathbf A$의 해를 찾으면 된다. 
	- 첫번째 원소가 이미 피벗 원소이고, 나머지 3개는 free variable이다. 따라서

$$ 
\begin{bmatrix}
\mathrm O \\
1 \\
0 \\
0 
\end{bmatrix}
\begin{bmatrix}
\mathrm O \\
0 \\
1 \\
0 
\end{bmatrix}
\begin{bmatrix}
\mathrm O \\
0 \\
0 \\
1 
\end{bmatrix}
$$

각각에 대해서 O를 채우면 되겠다. 모든 경우 O는 $-1$이다. 예를 들어, 

$$
\begin{bmatrix}
x \\
1 \\
0 \\
0 
\end{bmatrix}
\begin{bmatrix}
1 & 1 & 1 & 1 \\
\end{bmatrix} = 0
$$

* Column space of $\mathbf A$? 
	* $\mathcal C(\mathbf A) = \mathbb R^1$
	* $\mathcal N(\mathbf A) = \emptyset$


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ4Njc4ODMwM119
-->
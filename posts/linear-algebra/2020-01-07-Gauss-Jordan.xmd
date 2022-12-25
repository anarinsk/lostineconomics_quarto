---
toc: true
comments: true
layout: post 
title: Gauss-Jordan Elimination Algorithm
description: 가우스-조르단 소거법을 알아보자
categories: [math, matrix-theory]

---

## How to Solve Linear System 

- 1차 연립방정식을 풀기 위한 일종의 알고리듬이다. 
- 흔히 아는 연립방정식의 형태를 행렬식으로 표시해보자. 

$$
A x = b 
$$

- $A \in {\mathbb R}^{m \times n}$, $b \in  {\mathbb R}^{m \times 1}$
- 이때 $b$를 계수 행렬 $A$의 한 열로 편입한 형태를 augmented form이라고 부른다. 즉, 

$$
\begin{bmatrix}
A ~\vert ~ b
\end{bmatrix}
\in {\mathbb R}^{m \times (n +1)}
$$

- 해가 존재하면 일치성이 있다고 말하고 해가 존재하지 않으면 일치성이 없다고 말한다. 

## Row Echelon Form Matrix (REF)

- '열 사다리꼴' 행렬이라고 부른다. 정의는 다음과 같다 .

- 각 행에 0이 아닌 첫번째 원소를 "선행 원소" 혹은 피벗이라고 부른다. 
	- 선행원소 1을 조건으로 두는 경우가 있다. 이는 행 내에서 스케일링의 문제이다. 
- 각 선행원소는 앞선 행의 선행 원소보다 오른편에 위치해야 한다. 
	- 선행 원소가 없는 경우는 상관 없다.  
- 모든 행이 0인 행은 0이 아닌 행을 포함한 행보다 뒤쪽에 위치해야 한다. 

<p align="center"><kbd> <img src="https://github.com/anarinsk/lie-gauss_jordan/blob/master/assets/imgs/echelon.png?raw=true" width="400"> </kbd></p>


## Reduced Row Echelon Form Matrix (RREF)

- RREF가 되기 위한 조건은 다음과 같다.
	- REF다. 
	- 각 행의 선행 원소는 해당 열에서 유일한 0이 아닌 원소다. 
- 아래의 예를 확인하자. 

$$
\begin{bmatrix}
1 & 0 & \ast & 0 & \ast & \ast & 0 & 0 & \ast \\
0 & 1 & \ast & 0 & \ast & \ast & 0 & 0 & \ast     \\
0 & 0 & 0 & 1 & 0 & \ast & 0 & 0 & \ast   \\
0 & 0 & 0 & 0 & 0 & 0 & 1 &   0 & \ast   \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 & \ast   \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0   \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0  
\end{bmatrix}
$$

- 이 매트릭스에서 피봇이 되는 열의 경우 해당 열의 유일한 0이 아닌 원소는 1이 된다. 

## Matrix Operation 

- 연립방정식을 구하는 과정으로 여기면 쉽게 이해할 수 있다. 
	- 연립방정식이 주어졌을 때 해당 식의 순서를 바꾼다고 문제가 되지 않는다. 
	- 같은 행에서 일정한 수를 곱해도 무방하다 .
	- 한 행을 상수배 하여 다른 행에 더한다.

<p align="center"><kbd> <img src="https://github.com/anarinsk/lie-gauss_jordan/blob/master/assets/imgs/row_op.png?raw=true" width="450"> </kbd></p>

- 사실 우리가 중고등학교 때 배워왔던 1차 방정식의 해를 구하는 알고리듬 그대로다.

 
## Solution 

- 이렇게 구했을 때 RREF 행렬의 선행 원소, 즉 피벗은 그대로 맨 왼쪽 열의 가산된 항목을 해를 지닌다. 
	- 열로 생각해보자. RREF에서 피벗 열은 1인 한 개를 제외하면 모두 0이다. 따라서 해를 그대로 가중치로 지니게 된다. 
- 피벗이 아닌 경우는 어떤 값이 와도 상관 없다. 

## Inverse Matrix 

- 가우스-조르단 방법으로 역 행렬도 구할 수 있다. 
- 앞서 매트릭스 연산을 행렬로 나타낸 행렬을 기본 행렬(elementary matrix)라고 한다. 

$$
AX = I
$$

이때 $X = A^{-1}$로 둘 수 있다. 식의 양변에 동시에 기본 행렬 연산 $r$ 번을 전개한다고 하자. 

$$
\underbrace{E_r E_{r-1} \dotsb E_1}_{(*)} A X = E_r E_{r-1} \dotsb E_1 I
$$

이때 이 연산의 결과 식의 좌변이 $IX$로 바뀐다고 하자. 이는 다시 아래와 같다. 

$$
E_r E_{r-1} \dotsb E_1 A X = E_r E_{r-1} \dotsb E_1 I = IX
$$

$X = E_r E_{r-1} \dotsb E_1$이 되고, 이것이 곧 역행렬이다.  

&nbsp; 

## Reference 

[https://en.wikipedia.org/wiki/Gaussian_elimination](https://en.wikipedia.org/wiki/Gaussian_elimination)

---
toc: true
layout: post
comments: true
title: The College Wealth Divide
description: 미국 대졸자와 비대졸자의 투자 행태에 따른 부의 불평등 
categories: [economics, paper-summary]

---

## Source 

The College Wealth Divide: Education and Inequality in America, 1956-2016 [download]([https://www.stlouisfed.org/~/media/files/pdfs/hfs/is-college-worth-it/bartscher_kuhn_schularick_college_wealth_divide.pdf?la=en](https://www.stlouisfed.org/~/media/files/pdfs/hfs/is-college-worth-it/bartscher_kuhn_schularick_college_wealth_divide.pdf?la=en))
*Alina K. Bartscher, Moritz Kuhn, and Moritz Schularick*

## Addressing Issues 

- 새로운 설문 데이터의 발굴을 통해 대졸자와 비대졸자 사이의 소득과 부의 장기 추세를 살펴본다. 
- 대학 졸업에 따른 소득 프리미엄과 부 프리미엄의 패턴 차이가 확연히 존재하는데, 이러한 결과가 생긴 원인을 추적한다.

## Data 

- 미국 연준에서 다운로드 받을 수 있는 [Survey of Consumer Finances]([https://www.federalreserve.gov/econres/scfindex.htm](https://www.federalreserve.gov/econres/scfindex.htm))(SCF)라는 데이터가 있다. 이 데이터는 3년 간격으로 1983년부터 설문 자료를 수집하고 있는데, 여타 센서스와 같은 설문 항목과 비교해서 금용 관련된 상세한 내용을 담고 있다. 
- 그런데 SCF에 선배라고 할만한 자료가 1947년에서 1971년 사이 그리고 1977년에 대해서 미시건 대의 서베이 리서치 센터에 존재한다. Kuhn, Schularick, Steins가 이 두 자료를 코드 북에 기반해서 자료를 최대한 비슷하게 맞춰 결합했고, 이렇게 1949년~2016년의 전후 기간을 망라한 소득, 부 그리고 관련된 인구 통계적 정보를 담고 있는 데이터 셋이 만들어졌다. 저자들은 이를 SCF+라고 부른다.[^1]
[^1]:  매칭과 데이터 결합에 필요한 절차 및 기법은 논문에 비교적 상세하게 소개되어 있으니 관심 있는 분은 참조하시라. 

## Issues 

### Income premium vs wealth premium 

- 저자들의 관심사는 대졸자와 비대졸자(앞으로 혼란의 여지가 없을 때 각각 c(college), nc(noncollege)로 표기하겠다) 사이에 소득과 부의 차이가 역사적으로 어떻게 진화했는지를 파악하는 것이다. 우선 그림 1을 보자. 

<figure>
<figcaption>그림 1. 소득과 부의 역사적 변화 </figcaption>
<p align="center"><kbd>
  <img src="https://github.com/anarinsk/aps-college_wealth/blob/master/assets/imgs/K-001.png?raw=true" width="900">  
</kbd></p>
</figure>

- 그림1에서 $y$축은 1971년도 수준을 1로 두었을 때 각 연도의 소득과 부의 수준을 나타낸다. 시간에 흐름에 따라서 소득의 차이가 상대적으로 적게 벌어졌음에 반해서 부의 차이는 크게 벌어지고 있다. 특히 1980년대 이후 차이가 크게 벌어지고 있다. 

- 이는 소득과 부의 비율을 c와 nc로 나누어 비교한 그림2에서 보다 분명하게 드러난다.
 
 <figure>
<figcaption>그림 2. c와 nc의 부/소득의 역사적 변화 </figcaption>
<p align="center"><kbd>
  <img src="https://github.com/anarinsk/aps-college_wealth/blob/master/assets/imgs/K-002.png?raw=true" width="600">  
</kbd></p>
</figure>

### Decomposing wealth premium 

$$
\dfrac{\overline{W}_{e,t}}{\overline{W}_{e,71}} = \dfrac{\sum^{3}_{i=1} s_{e,i,t} \overline{W}_{e,i,t}}{\overline{W}_{e,71}} = \sum^{3}_{i=1} s_{e,i,t} \dfrac{\overline{W}_{e,i,71}}{\overline{W}_{e,71}} \dfrac{\overline{W}_{e,i,t}}{\overline{W}_{e,i,71}}
$$
 - 변수 
	 - $\overline {W}_\cdot$: 해당 집단이 보유한 평균 부 
	 - $s_\cdot$: 해당 부 계층의 비율. 
		 - $s_{c, 1, 81}$이라면 1981년도 c에 속한 사람들 중에서 전체 부의 계층 1에 속하는 비율을 나타낸다. 
		
 - 인덱스 
	 - $e = {\rm c, nc}$
	 - $t =$ 56, 61, 66, 71, 76, 81, 86, 91, 96, 01, 06,11, 16
	 - $i = 1, 2, 3$

- $e$는 c와 nc의 구분을 $t$는 연도, 그리고 $i$는 세 가지로 구분한 부 계층을 구분하기 위한 인덱스다. 1은 하위 50%, 2는 중위 50%~90%, 그리고 3은 상위 10%를 각각 나타낸다. 
- 분해 식을 통해서 크게 세가지 변동을 구분할 수 있다. 
	- $s$의 변화 
	- $$\dfrac{\overline{W}_{e,i,71}}{\overline{W}_{e,71}}$$: 기준 연도의 부 계층의 차이 
	-  $$\dfrac{\overline{W}_{e,i,t}}{\overline{W}_{e,i,71}}$$: 기준 연도 대비 특정 부 계층의 연도별 변화 

- 이 세 가지에 분해 요소 중에서 시간을 따라가지 않은 두 번째를 제외하고 나머지에 대해서 반사실(counterfactual)을 적용해보자. 

- Counterfactual 1
$$
\dfrac{\overline{W}_{x,i,t}}{\overline{W}_{x,i,71}} = 
\begin{cases}
\dfrac{\overline{W}_{nc,i,t}}{\overline{W}_{nc,i,71}} & \text{if $x = \rm{c}$} \\
\dfrac{\overline{W}_{c,i,t}}{\overline{W}_{c,i,71}}  & \text{if $x = \rm{nc}$} 
\end{cases}
$$

- Counterfactual 2
    - $s_{x,i,t}$ 대신 $s_{x,i,71}$을 적용한다. 즉, 시간이 지나면서 학력별 부 계급의 분포가 1971년도 지표에 고정되어 있었을 상황을 대입해본다. 이는 시간이 지나면서 소득 불평등의 패턴이 n, nc 사이에 차별적으로 타나났는지를 추적한다. 
    - 같은 맥락에서 n와 nc의 $s$를 바꾸는 분석도 해볼 수 있을 듯 한데, 저자들이 시도하지는 않았다. 

<figure>
<figcaption>그림 3. c와 nc의 변화는 어디에서 왔는가? </figcaption>
<p align="center"><kbd>
  <img src="https://github.com/anarinsk/aps-college_wealth/blob/master/assets/imgs/K-003.png?raw=true" width="900">  
</kbd></p>
</figure>

- 그림 3의 A는 c의 부에 대해서 반사실 1, 2 그리고 1+2를 적용했을 때의 변화를 나타낸다. 반사실 1의 영향이 크고, 반사실 2는 거의 영향을 주지 않았다. 이를 통해 시간이 지나면서 c의 경우 nc에 비해서 더 많은 부를 축적했음을 보여준다. 반면, 코호트(n, nc) 내에서 부의 계층 변화는 거의 영향을 주지 않았다. 
- 한편, nc의 경우는 반사실 1과 반사실 2가 모두 부의 축적에 악영향을 주었음을 알 수 있다. 
- 각 코호트별로 부의 계층별 점유율 변화는 그림 4와 같다. 

<figure>
<figcaption>그림 4. c와 nc 내의 소득 계층별 비율의 역사적 변화 </figcaption>
<p align="center"><kbd>
  <img src="https://github.com/anarinsk/acs-college_wealth/blob/master/assets/imgs/K-004.png?raw=true" width="900">  
</kbd></p>
</figure>

- 그림에서 보듯이 c의 경우 연도 변화에 따른 계층별 변화가 크지 않다. nc의 경우 상위 10%에 속하는 비율이 경향적으로 낮아지고 있다. 

<figure>
<figcaption>그림 5. 소득 계층별 c/nc 비율의 역사적 변화 </figcaption>
<p align="center"><kbd>
  <img src="https://github.com/anarinsk/aps-college_wealth/blob/master/assets/imgs/K-005.png?raw=true" width="900">  
</kbd></p>
</figure>

- 그림 5는 전체 인구에서 c가 차지하는 비중의 연도별 변화와 중간 계층(50~90%)의 변화가 비슷하게 진행되었음을 알 수 있다. 반면 c의 경우 50% 아래로 떨어지기보다는 상위 10%로 진입한 경향이 많았다는 점도 확인할 수 있다. 

## Regression analysis 

- 대학 졸업 여부가 어느 측면에서 부의 축적에 영향을 주었는지 살펴보기 위해서 계량적 분석을 시도 했다. 즉, c 여부가 부의 증가에 어떻게 영향을 주었는가를 보다 면밀하게 살펴보는 것이 분석의 목표다. 

<figure>
<figcaption>그림 6. c/nc의 소득 비율과 부 비율의 역사적 변화 </figcaption>
<p align="center"><kbd>
  <img src="https://github.com/anarinsk/aps-college_wealth/blob/master/assets/imgs/K-007.png?raw=true" width="900">  
</kbd></p>
</figure>

- 그림 6은 c와 nc의 격차를 소득과 부 각각에 관해 표시한 것이다. 앞서 보았듯이 1980년대 이전까지는 소득과 부 모두 1 주변에 머물다가 1980년대 이후 부의 증가가 점점 격차를 벌이며 증가하는 추세를 보이고 있다. 혹시 이러하는 추세가 c에 속한 상위 10%의 보다 빠른 부의  축적 때문이었을까? 코호트를 중위 소득 계층(50~90%)으로 제한해서 살펴보면 그림 7과 같다. 그림에서 보듯이 c의 자산 증가는 최상 계층의 현상이 아닌 일반적인 추세였다고 볼 수 있겠다. 

<figure>
<figcaption>그림 7. 50~90% 부 계층의 소득 및 부 수준의 역사적 변화 (10년 단위)</figcaption>
<p align="center"><kbd>
  <img src="https://github.com/anarinsk/aps-college_wealth/blob/master/assets/imgs/K-008.png?raw=true" width="900">  
</kbd></p>
</figure>

- 질문은 무엇이 c의 빠른 부의 축적을 낳았는가, 하는 대목이다. 일반 기본적으로 살펴본 회귀 식은 다음과 같다. 

$$
W_{it} = \alpha_0 + \underbrace{\beta_1 c_{it}}_{A} + \underbrace{\sum_{t > 1956} \beta_{2,t}~\mathbb{I}_{year = t} \cdot c_t}_{B} +  \underbrace{\sum_{t > 1956} \beta_{3,t}~\mathbb{I}_{year = t}}_{C} + \underbrace{\Gamma' X_{it}}_{D} + \xi_{it} 
$$

* 회귀분석의 각 부분을 간략하게 살펴보자. 
	* A: 대학 졸업 여부가 전체 기간에 걸쳐 부에 미치는 효과
	* B: 연도별로 구분된 대학 졸업 여부가 부에 미치는 효과 
	* C: 연도별 효과가 부에 미치는 효과 
	* D: 통제 변수 (소득수준, 결혼 여부, 자녀 유무 등) 

* 부에 c가 미치는 효과는 $\beta_1 + \beta_{2,t}$로 연도별로 측정할 수 있다. 

<figure>
<figcaption>그림 8. c의 부 관련 회귀 계수의 역사적 변화 </figcaption>
<p align="center"><kbd>
  <img src="https://github.com/anarinsk/aps-college_wealth/blob/master/assets/imgs/K-010.png?raw=true" width="600">  
</kbd></p>
</figure>

- 그림 8에서 보듯이 c의 효과는 분명하다. 다만 소득 계층 기준으로 전체 집단의 효과가 50~90%의 중간 층에 비해  강하게 나타고 있다. 그림 9를 통해 이 내용을 다시 살펴보자. 

<figure>
<figcaption>그림 9. c의 부와 소득 회귀 계수의 비교 </figcaption>
<p align="center"><kbd>
  <img src="https://github.com/anarinsk/aps-college_wealth/blob/master/assets/imgs/K-009.png?raw=true" width="900">  
</kbd></p>
</figure>

- 그림 9는 소득 계층별로 나누어 결과를 나타내고 있다. 왼쪽은 좌변의 종속 변수가 부이고 오른쪽은 종속 변수가 소득이다.
	- c에 대해서 부의 효과가 전반적으로 높으며 특히 상위 10%에 두드러진다. 
	- 소득에 대해서는 이러한 효과가 나타나지 않는다. 특히 상위 10%를 제외하면 c의 소득 증가 효과는 거의 없다고 봐도 좋다.  

- 논문에서는 이러한 c의 효과가 어디서 비롯하는지를 조금 더 탐구하고 있다.  자료의 한계 때문에 상세하게 추적하지는 못한다. 다만 c와 nc 사이에 존재하는 중요한 차이로 금융 지식(financial literacy)의 차이를 지목하고 있다. 즉, 소득을 투자로 전환할 수 있는 수단을 알고 있었는지 여부가 중요하다는 것이다. 논문에서 주목한 또 하나의 차이는 사업체의 소유 여부다. 이 역시 부의 차이를 만들어내는 데 일정한 역할을 한다. 

- 논문에서 제기한 또 하나의 흥미로운 질문은 금융 지식의 여부가 c와 nc 사이에 세분화되어 있는지 여부다. 다시 말하면, 두 코호트가 같이 금융 상품에 투자했다면, 누가 더 잘 하는가에 관한 것이다. 

<figure>
<figcaption>그림 10. 금융 및 사업 관련 부의 수익률 비교 </figcaption>
<p align="center"><kbd>
  <img src="https://github.com/anarinsk/aps-college_wealth/blob/master/assets/imgs/K-012.png?raw=true" width="900">  
</kbd></p>
</figure>

- 그림 10의 A에 따르면 사업체 보유자와 미 보유자 사이에는 수익률 차이가 존재한다. 하지만 n와 nc 사이에 차이는 거의 없다. 나머지 그림에서도 n와 nc 사이에 뚜렷한 차이를 발견하기 힘들다. 즉 c와 nc 사이의 금융 지식의 차이란 투자 대상의 인지 및 실행과 같은 차원일 가능성이 높다는 것이다. 

## Extra

- 개인적으로 재미있게 본 내용 하나 추가한다. 유유상종 혼(assortative marriage)이 존재하는지 여부에 관한 것이다. 
	- 교육 년수를 12년 미만(중퇴), 고졸, 대졸로 구분하면 3X3 테이블이 나온다. 
	- 이제 각각의 경우에 해당하는 부부의 비율을 구한다. 
	- 각각의 인구 비율이 무작위로 매칭되었을 때의 비율을 구한다. 
	- 실제의 유유상종 혼의 비율과 무작위의 비율을 비교하면 유유상종의 정도가 계산된다. 

- 논문에서 밝힌 바에 따르면 대졸자의 유유상종 혼은 줄어드는 추세다. 즉, 1965년에 위 비율은 5.9였는데, 2016년에는 1.8에 불과하다. 즉 유유상종 혼은 감소하는 추세다. 

- 다음으로 유유상종 혼이 부의 창출에 있어서 단순 합을 넘어서는 추가적인 이득을 제공하는가 여부에 관한 것이다.  

<figure>
<figcaption>그림 11. 유유상종 혼은 부의 형성에 어떻게 영향을 주었는가 </figcaption>
<p align="center"><kbd>
  <img src="https://github.com/anarinsk/aps-college_wealth/blob/master/assets/imgs/K-006.png?raw=true" width="900">  
</kbd></p>
</figure>

- A, B에서 보듯이 소득과 부 모두 유유상종 혼 상태의 가구가 평균보다 두 배 가량 높다. 하지만 C, D에서 보듯이 이를 각 해당 연도의 유유상종 혼 인구가 점유한 부의 비율과 유유상종 혼 인구의 비율로 나눈 수치는 거의 일정한 수준을 유지하고 있다. 

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzMjU2Mzk5MzIsNDkyNzA3MTQ4LC0yNj
MwNDU3NjYsMTIxNTEzNzcxN119
-->
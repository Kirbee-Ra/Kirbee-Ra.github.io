k 계산법
=

## 목차
- [물리량의 조작적 정의]
- [본디의 k-인자]
- [시간 지연]
- [로런츠 변환]
- [속도 변환]
- [길이 수축]

---

## k 계산법

..
기존의 특수 상대성 이론에 대한 지식을 먼저 학습한 뒤 보는 것이 좋습니다.

---

## 물리량의 조작적 정의

상대성 원리로부터 시공간에 대한 이론을 구축하기 위해서는 거리에 대한 개념을 재정의할 필요가 있습니다.
상대성 이론에서 거리는 자명한 개념이 아니므로 **조작적 정의(Operational Definition)**를 통해 측정해야 합니다.
조작적 정의란 구체적인 실험 등의 절차를 통해 측정하여 정의하는 것입니다.

### 동시성

거리에 대한 정의를 하기 전에 **동시성(Simultaneity)**에 대한 정의를 먼저 해야 합니다.
고전 이론에 의하면, 거리는 두 관찰자의 운동 상태에 관계 없이 두 관찰자가 '동시'에 측정한 위치 사이의 간격으로 정의됩니다.
즉, 동시성에 대한 정의를 먼저 해야 관찰자들의 운동 상태에 관계 없이 거리라는 개념을 정의할 수 있습니다.

Milne과 Bondi가 제시한 정의를 이용해봅시다.
Milne은 관찰자가 '시계'와 '빛 신호'를 이용하여 근처에서 발생한 사건의 시각을 빛 신호를 주고 받으며 측정할 수 있다고 주장합니다.
맥스웰 방정식이 모든 관성 좌표계에 대해 성립하므로 다음과 같습니다.

- 광속은 광원이나 관찰자의 운동 상태와 관계 없이 일정하다.

다음 그림과 같이 등속도 운동하는 관찰자가 시각 $$t=t_1$$에서 빛 신호를 보냈다고 해봅시다.

(Milne def)

그리고 보낸 신호가 사건 $$A$$에 도달하고, 시각 $$t=t_2$$때 되돌아왔다고 해봅시다.
광속이 일정하다면, 광자가 방출된 후 사건 $$A$$에 도달할 때와 그 시점에서 다시 되돌아올 때까지의 시간이 같을 것입니다.
그러면 관찰자가 시각 $$t=\displaystyle\frac{1}{2}\left(t_1+t_2\right)$$에서 발생한 사건 $$B$$와 사건 $$A$$가 동시에 일어났다고 느낄 것입니다.
그 관찰자는 사건 $$A$$가 시각 $$t=\displaystyle\frac{1}{2}\left(t_1+t_2\right)$$에서 발생했다고 말할 수 있습니다.
이를 **동시성의 레이더 정의(Radar Definition of Simultaneity)**라고 합니다.

---

### 본디의 k-인자

---

## 시간 지연

---

## 2차원 로런츠 변환

이제 k 계산법에서 로런츠 변환을 어떻게 유도하는지 알아봅시다.
다음 그림과 같이 관찰자 $$O$$에 대해 관찰자 $$O'$$이 속도 $$u$$로 운동하고 있다고 해봅시다.

(wl)

계산의 편의성을 위해 두 관찰자가 만나는 사건인 $$E$$에서 두 관찰자 모두 자신들의 시계의 영점을 맞췄다고 해봅시다.
이제 시각 $$t=T$$에서 관찰자 $$O$$가 관찰자 $$O'$$에게 빛 신호를 보냈다고 해봅시다.
그리고 이 빛 신호는 $$t'=kT$$에 $$O'$$를 지날 것이고, 사건 $$B$$에서 반사되어 시각 $$t'=T'$$때 $$O'$$을 다시 지난 뒤, 시각 $$t=kT'$$때 다시 돌아옵니다.
관찰자 $$O$$의 입장에서 사건 $$B$$는 동시성의 레이더 정의에 의해 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
			t=\frac{1}{2}\left(T+kT'\right)\\
			x=\frac{1}{2}c\left(kT'-T\right)
		\end{cases}
$$

마찬가지로 관찰자 $$O'$$의 입장에서는 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
			t=\frac{1}{2}\left(kT+T'\right)\\
			x=\frac{1}{2}c\left(T'-kT\right)
		\end{cases}
$$

행렬로 나타내면 다음과 같습니다.

$$
\begin{cases}
			\begin{bmatrix}
				ct\\
				x
			\end{bmatrix}=\displaystyle\frac{c}{2}\begin{bmatrix}
				1&k\\
				-1&k
			\end{bmatrix}\begin{bmatrix}
				T\\
				T'
			\end{bmatrix}\\
			\begin{bmatrix}
				ct'\\
				x'
			\end{bmatrix}=\displaystyle\frac{c}{2}\begin{bmatrix}
				k&1\\
				-k&1
			\end{bmatrix}\begin{bmatrix}
				T\\
				T'
			\end{bmatrix}
		\end{cases}
$$

관찰자 $$O'$$에 대한 식을 다음과 같이 나타내봅시다.

$$
\begin{align*}
		\begin{bmatrix}
			T\\
			T'
		\end{bmatrix}&=\frac{2}{c}\begin{bmatrix}
			k&1\\
			-k&1
		\end{bmatrix}^{-1}\begin{bmatrix}
			ct'\\
			x'
		\end{bmatrix}\\
		&=\frac{1}{kc}\begin{bmatrix}
			1&-1\\
			k&k
		\end{bmatrix}\begin{bmatrix}
			ct'\\
			x'
			\end{bmatrix}
	\end{align*}
$$

이를 관찰자 $$O$$에 대한 식에 대입하면 다음과 같습니다.

$$
	\begin{align*}
		\begin{bmatrix}
			ct\\
			x
		\end{bmatrix}&=\displaystyle\frac{c}{2}\begin{bmatrix}
			1&k\\
			-1&k
		\end{bmatrix}\frac{1}{kc}\begin{bmatrix}
		1&-1\\
		k&k
		\end{bmatrix}\begin{bmatrix}
		ct'\\
		x'
		\end{bmatrix}\\
		&=\frac{1}{2k}\begin{bmatrix}
			k^2+1&k^2-1\\
			k^2-1&k^2+1
		\end{bmatrix}\begin{bmatrix}
			ct'\\
			x'
		\end{bmatrix}\\
		&=\frac{1}{2}\begin{bmatrix}
			k+k^{-1}&k-k^{-1}\\
			k-k^{-1}&k+k^{-1}
		\end{bmatrix}\begin{bmatrix}
			ct'\\
			x'
		\end{bmatrix}
	\end{align*}
$$

$$k+k^{-1}$$과 $$k-k^{-1}$$은 각각 다음과 같습니다.

$$
\begin{align*}
		&k+k^{-1}=\sqrt{\frac{1+\beta}{1-\beta}}+\sqrt{\frac{1-\beta}{1+\beta}}=\frac{2}{\sqrt{1-\beta^2}}\\
		&k-k^{-1}=\sqrt{\frac{1+\beta}{1-\beta}}-\sqrt{\frac{1-\beta}{1+\beta}}=\frac{2\beta}{\sqrt{1-\beta^2}}
	\end{align*}
$$

이를 대입하면 다음과 같습니다.

$$
\begin{align*}
		\begin{bmatrix}
			ct\\
			x
		\end{bmatrix}&=\frac{1}{2}\begin{bmatrix}
			\displaystyle\frac{2}{\sqrt{1-\beta^2}}&\displaystyle\frac{2\beta}{\sqrt{1-\beta^2}}\\
			\displaystyle\frac{2\beta}{\sqrt{1-\beta^2}}&\displaystyle\frac{2}{\sqrt{1-\beta^2}}
		\end{bmatrix}\begin{bmatrix}
			ct'\\
			x'
		\end{bmatrix}\\
		&=\frac{1}{\sqrt{1-\beta^2}}\begin{bmatrix}
			1&\beta\\
			\beta&1
		\end{bmatrix}\begin{bmatrix}
		ct'\\
		x'
		\end{bmatrix}
	\end{align*}
$$

여기서 $$\displaystyle\frac{1}{\sqrt{1-\beta^2}}$$은 로런츠 인자 $$\gamma$$이므로 로런츠 변환은 다음과 같습니다.

$$
\begin{bmatrix}
			ct\\
			x
		\end{bmatrix}=\gamma\begin{bmatrix}
			1&\beta\\
			\beta&1
		\end{bmatrix}\begin{bmatrix}
		ct'\\
		x'
		\end{bmatrix}
$$

이는 시간 1차원과 공간 1차원에 대한 식이므로 2차원 로런츠 변환입니다.

### 로런츠 역변환

역변환은 간단합니다.
다음과 같이 나타낼 수 있습니다.

$$
\begin{align*}
		\begin{bmatrix}
			ct'\\
			x'
		\end{bmatrix}&=\frac{1}{\gamma\left(1-\beta^2\right)}\begin{bmatrix}
			1&-\beta\\
			-\beta&1
		\end{bmatrix}\begin{bmatrix}
		ct\\
		x
		\end{bmatrix}\\
		&=\gamma\begin{bmatrix}
			1&-\beta\\
			-\beta&1
		\end{bmatrix}\begin{bmatrix}
			ct\\
			x
		\end{bmatrix}
	\end{align*}
$$

관찰자 $$O$$가 $$O'$$에 대해 $$-x'$$방향으로 동일한 속력 $$u$$로 운동하는 것입니다.

### 고전 역학으로의 근사

시간에 대한 식의 양 변을 $$c$$로 나누면 다음과 같습니다.

$$
\begin{bmatrix}
			t\\
			x
		\end{bmatrix}=\gamma\begin{bmatrix}
			1&\displaystyle\frac{\beta}{c}\\
			\beta&1
		\end{bmatrix}\begin{bmatrix}
		t'\\
		x'
		\end{bmatrix}
$$

극한 $$c\rightarrow\infty$$를 취하면 다음과 같습니다.

$$
	\begin{align*}
		&\lim_{c\rightarrow\infty}\gamma=1\\
		&\lim_{c\rightarrow\infty}\gamma\beta=0\\
		&\lim_{c\rightarrow\infty}\begin{bmatrix}
			t\\
			x
		\end{bmatrix}=\begin{bmatrix}
			1&0\\
			u&1
		\end{bmatrix}\begin{bmatrix}
			t'\\
			x'
		\end{bmatrix}
	\end{align*}
$$

이는 고전 역학에서의 갈릴레이 변환과 일치합니다.

---

## 속도 변환

어떤 입자가 관찰자 $$O$$에 대해 $$-x$$방향으로 일정한 속력 $$v$$로 운동한다고 해봅시다.
고전 역학에서는 관찰자 $$O'$$가 측정한 입자의 속도는 $$u+v$$입니다.
하지만 특수 상대성 이론에서는 다릅니다.
입자가 $$x(0)=a$$에서 출발할 때, 이 입자의 궤적은 다음과 같습니다.

$$
x=-vt+a
$$

이를 로런츠 변환 식에 대입하면 다음과 같습니다.

$$
\begin{bmatrix}
		ct'\\
		x'
	\end{bmatrix}=\gamma\begin{bmatrix}
	1&-\beta\\
	-\beta&1
	\end{bmatrix}\begin{bmatrix}
	ct\\
	-vt+a
	\end{bmatrix}
$$

이 식의 미분은 다음과 같습니다.

$$
\begin{bmatrix}
		cdt'\\
		dx'
	\end{bmatrix}=\gamma\begin{bmatrix}
	1&-\beta\\
	-\beta&1
	\end{bmatrix}\begin{bmatrix}
	cdt\\
	-vdt
	\end{bmatrix}
$$

---

## $$4$$차원 로런츠 변환

시공간은 시간 $$1$$차원과 공간 $$3$$차원의 $$4$$으로 이루어져 있습니다.
이 $$4$$차원 시공간에서 로런츠 변환이 어떻게 나타나는지 알아봅시다.

### $$4$$차원 좌표 변환

로런츠 변환을 유도하기 전에 먼저 $$4$$차원 좌표 변환에 대해 알아봅시다.
두 관찰자 $$O$$에 의해 기술되는 좌표 $$\left(t,x,y,z\right)$$와 관찰자 $$O'$$에 의해 기술되는 좌표 $$\left(t',x',y',z'\right)$$ 사이의 좌표 변환을 알아보기 위해 다음과 같은 가정을 해봅시다.

- 이 좌표 변환은 아핀 변환이며 다음과 같은 형태로 나타납니다.

$$
\begin{bmatrix}
	ct\\
	x\\
	y\\
	z
\end{bmatrix}=\mathbf{L}\begin{bmatrix}
ct'\\
x'\\
y'\\
z'
\end{bmatrix}+\mathbf{C}
$$

여기서 $$\mathbf{L}$$은 $$4\times4$$의 가역 행렬이며, $$\mathbf{C}$$는 열벡터입니다.
- 광자는 관성 좌표계에 관계 없이 광속 $$c$$로 직선 경로를 따라 운동합니다. 경로는 다음과 같이 나타낼 수 있습니다.

$$
\begin{align*}
&\begin{cases}
	x=u_1t+a_1\\
	y=u_2t+a_2\\
	z=u_3t+a_3
\end{cases}\\
&c=\sqrt{u_1^2+u_2^2+u_3^2}
\end{align*}
$$

여기서 $$u_1,u_2,u_3,a_1,a_2,a_3$$는 모두 상수입니다.

- 그 어떤 물리적 효과도 빛보다 빠르지 않습니다.
- 상대성 원리가 모든 물리적 현상에 적용됩니다. 즉, 가속하지 않는 두 관찰자 사이의 상대적인 운동은 실험을 통해 관측될 수 있습니다.

첫번째 가정은 뉴턴의 관성의 법칙이 한 관성 좌표계에서 성립하면, 다른 관성 좌표계에서도 성립하게 합니다.
외력이 작용하지 않는 입자는 시공간의 직선 경로를 따라 등속으로 운동합니다.
두번째 가정은 광속이 관찰자와 독립적이라는 것입니다.
빛이 관성 좌표계에서 맥스웰 방정식을 따른다면 성립합니다.
세번째 가정은 일관성을 위해 필요합니다.

### 광추와 민코프스키 공간

이제 행렬 $$\mathbf{L}$$의 성분을 유도해봅시다.
행렬 $$\mathbf{L}$$와 열벡터 $$\mathbf{C}$$를 다음과 같이 쓸 수 있습니다.

$$
	\begin{align*}
&\mathbf{L}=\begin{bmatrix}
			L_{00}&L_{01}&L_{02}&L_{03}\\
			L_{10}&L_{11}&L_{12}&L_{13}\\
			L_{20}&L_{21}&L_{22}&L_{23}\\
			L_{30}&L_{31}&L_{32}&L_{33}
		\end{bmatrix}\\
&\mathbf{C}=\begin{bmatrix}
			C_0\\
			C_1\\
			C_2\\
			C_3
		\end{bmatrix}
  		\end{align*}
$$

따라서 좌표 변환을 다음과 같이 나타낼 수 있습니다.

$$
\begin{bmatrix}
	ct\\
	x\\
	y\\
	z
\end{bmatrix}=\begin{bmatrix}
L_{00}&L_{01}&L_{02}&L_{03}\\
L_{10}&L_{11}&L_{12}&L_{13}\\
L_{20}&L_{21}&L_{22}&L_{23}\\
L_{30}&L_{31}&L_{32}&L_{33}
\end{bmatrix}\begin{bmatrix}
ct'\\
x'\\
y'\\
z'
\end{bmatrix}+\begin{bmatrix}
C_0\\
C_1\\
C_2\\
C_3
\end{bmatrix}
$$

우선 $$L_{00}$$을 먼저 고려해봅시다.
$$O'$$은 자신의 세계선에서 $$\left(ct',0,0,0\right)$$에 위치하고 있습니다.
따라서 시간 사이의 관계식은 다음과 같습니다.

$$
ct=L_{00}ct'+C_0
$$

시간 지연을 떠올리면 다음과 같은 관계식이 자연스럽게 유도됩니다.

$$
\begin{align*}
&L_{00}=\gamma\\
&\rightarrow ct=L_{00}ct'+C_0
\end{align*}
$$

역변환에 대해서도 생각해봅시다.
이때는 $$O$$가 자신의 세계선에서 $$\left(ct,0,0,0\right)$$에 위치하고 있습니다.
$$\gamma'$$이 행렬 $$\mathbf{L}^{-1}$$의 $$00$$번째 성분이라면, 비슷한 관계식으로 나타낼 수 있습니다.

$$
ct'=\gamma'ct+C_0'
$$

$$\gamma$$와 $$\gamma'$$은 두 관찰자의 상대적인 운동에만 의존하는 양입니다.
따라서 다음과 같습니다.

$$
\gamma=\gamma'
$$


두번째 가정을 살펴봅시다.
빛이 사건 $$A$$를 통과한다고 해봅시다.
그렇다면, 이 빛은 다음과 같이 원뿔 모양의 세계선을 형성합니다.

(light cone)

이를 **광추(Light Cone)**라고 합니다.
사건 $$A$$가 $$t=x=y=z=0$$이라고 해봅시다.
사건 $$A$$에서의 광추의 방정식은 다음과 같습니다.

$$
c^2t^2-x^2-y^2-z^2=0
$$

$$3$$차원에서의 원뿔의 방정식을 $$4$$차원 시공간으로 확장한 것이라고 보시면 됩니다.
이 광추는 두 영역으로 나뉩니다.
하나는 사건 $$A$$로부터 광자가 출발했을 때 광자가 도달할 수 있는 모든 '미래'의 영역입니다.
광자는 사건 $$A$$로부터 공간상의 모든 방향으로 나아갈 수 있습니다.

(light cone)

사건 $$A$$로부터 출발하는 순간, $$t>0$$이 되므로 미래의 영역입니다.

(light cone)

또 다른 하나는 광자가 사건 $$A$$에 도달했을 때 광자가 지나올 수 있는 모든 '과거'의 영역입니다.
광자는 공간상의 임의의 위치로부터 사건 $$A$$에 도달할 수 있습니다.

(light cone)

사건 $$A$$에 도달하기 전에는 $$t<0$$이므로 과거의 영역입니다.

(light cone)

광추는 원점으로부터 시간에 따라 광속 $$c$$로 퍼집니다.
즉, 구형의 파면을 형성하게 됩니다.
이렇게 특수 상대성 이론에서 기술하는 시공간을 **민코프스키 공간(Minkowski Space)**이라고 합니다.

### 4차원 로런츠 변환

두 사건 $$E_1$$과 $$E_2$$를 생각해봅시다.
관찰자 $$O$$는 두 사건의 좌표를 다음과 같이 기술합니다.

$$
	\begin{align*}
&E_1:\left(t_1,x_1,y_1,z_1\right)\\
&E_2:\left(t_2,x_2,y_2,z_2\right)
\end{align*}
$$

관찰자 $$O'$$은 두 사건의 좌표를 다음과 같이 기술합니다.

$$
	\begin{align*}
&E_1:\left(t_1',x_1',y_1',z_1'\right)\\
&E_2:\left(t_2',x_2',y_2',z_2'\right)
\end{align*}
$$

두 사건이 광자의 세계선 위에 위치한다면, 다음의 방정식과 동치입니다.

$$
c^2\left(t_2-t_1\right)^2-\left(x_2-x_1\right)^2-\left(y_2-y_1\right)^2-\left(z_2-z_1\right)^2=0
$$

두 사건이 광자의 세계선 위에 위치한다는 것은 관성 좌표계와는 상관 없이 이와 같은 식으로 나타낼 수 있습니다.
따라서 다음의 식도 성립합니다.

$$
c^2\left(t_2'-t_1'\right)^2-\left(x_2'-x_1'\right)^2-\left(y_2'-y_1'\right)^2-\left(z_2'-z_1'\right)^2=0
$$

위 식을 간단히 쓰기 위해 다음의 두 벡터를 이용해봅시다.

$$
	\begin{align*}
&\mathbf{X}=\begin{bmatrix}
	ct_2\\
	x_2\\
	y_2\\
	z_2
\end{bmatrix}-\begin{bmatrix}
ct_1\\
x_1\\
y_1\\
z_1
\end{bmatrix}\\
&\mathbf{X}'=\begin{bmatrix}
	ct_2'\\
	x_2'\\
	y_2'\\
	z_2'
\end{bmatrix}-\begin{bmatrix}
	ct_1'\\
	x_1'\\
	y_1'\\
	z_1'
\end{bmatrix}
\end{align*}
$$

그리고 다음과 같이 대각 행렬 $$\mathbf{g}$$를 정의해봅시다.

$$
\mathbf{g}=\begin{bmatrix}
	1&0&0&0\\
	0&-1&0&0\\
	0&0&-1&0\\
	0&0&0&-1
\end{bmatrix}
$$

따라서 두 사건에 대한 식은 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
	\mathbf{X}^T\mathbf{g}\mathbf{X}=0\\
	\mathbf{X}'^T\mathbf{g}\mathbf{X}'=0
\end{cases}
$$

$$\mathbf{X}$$와 $$\mathbf{X}'$$은 로런츠 변환 관계에 있습니다.

$$
\mathbf{X}=\mathbf{L}\mathbf{X}'
$$

$$\mathbf{X}^T$$는 다음과 같습니다.

$$
\mathbf{X}^T=\mathbf{X}'^T\mathbf{L}^T
$$

따라서 다음과 같이 쓸 수 있습니다.

$$
\mathbf{X}'^T\mathbf{L}^T\mathbf{g}\mathbf{L}\mathbf{X}'=0
$$

다음 식과 비교해봅시다.

$$
\mathbf{X}'^T\mathbf{g}\mathbf{X}'=0
$$

두 식은 동치입니다.
이런 경우는 다음을 만족하는 $$0$$이 아닌 실수 $$\alpha$$가 존재합니다.

$$
\mathbf{L}^T\mathbf{g}\mathbf{L}=\alpha\mathbf{g}
$$

로런츠 변환은 가역 행렬이어야 하기 때문에 $$\alpha$$는 $$0$$이면 안됩니다.
역변환은 다음과 같습니다.

$$
\mathbf{L}^{-1}=\alpha^{-1}\mathbf{g}^{-1}\mathbf{L}^T\mathbf{g}
$$

여기서 $$\mathbf{g}^{-1}=\mathbf{g}$$이므로 다음과 같습니다.

$$
\mathbf{L}^{-1}=\alpha^{-1}\mathbf{g}\mathbf{L}^T\mathbf{g}
$$

역변환의 $$00$$번째 성분이 $$\gamma/\alpha$$임이 드러났습니다.
이는 이전에 언급한 $$\gamma'$$이었고, $$\gamma$$와 동일했습니다.
따라서 $$\alpha=1$$입니다.
그러므로 다음과 같습니다.

$$
\mathbf{L}^T\mathbf{g}\mathbf{L}=\mathbf{g}
$$

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

- 이 좌표 변환은 아핀 변환이며 다음과 같은 형태로 나타납니다: $$\displaystyle\begin{bmatrix}
	ct\\
	x\\
	y\\
	z
\end{bmatrix}=\mathbf{L}\displaystyle\begin{bmatrix}
ct'\\
x'\\
y'\\
z'
\end{bmatrix}+\mathbf{C}$$.
여기서 $$\mathbf{L}$$은 $$4\times4$$의 가역 행렬이며, $$\mathbf{C}$$는 열벡터입니다.
- 

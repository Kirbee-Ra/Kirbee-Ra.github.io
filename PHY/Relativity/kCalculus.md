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

다음 그림과 같이 등속도 운동하는 관찰자가 시각 $$t=t_1$$에서 거울을 향해 빛 신호를 보냈다고 해봅시다.

(Milne def)

그리고 보낸 신호가 사건 $$A$$에 도달하고, 시각 $$t=t_2$$때 되돌아왔다고 해봅시다.
거울에는 관찰자가 갖고 있는 시계와 같은 관성 좌표계에서 동기화된 시계가 있다고 해봅시다.
그리고 빛이 거울에 도달한 순간, 그 시각이 기록됩니다.
관찰자의 시계와 동기화 되어있으므로 관찰자의 시계 또한 그 순간을 기록합니다.
이 사건을 $$B$$라고 해봅시다.
광속이 일정하다면, 광자가 방출된 후 사건 $$A$$에 도달할 때와 그 시점에서 다시 되돌아올 때까지의 시간이 같을 것입니다.
그러면 관찰자는 사건 $$B$$가 시각 $$t=\displaystyle\frac{1}{2}\left(t_1+t_2\right)$$에서 발생했다고 관측합니다.
그 관찰자는 사건 $$A$$가 시각 $$t=\displaystyle\frac{1}{2}\left(t_1+t_2\right)$$에서 발생했다고 말할 수 있습니다.
두 사건은 동시에 발생했고, 이 식을 **동시성의 레이더 정의(Radar Definition of Simultaneity)**라고 합니다.
이 식은 모든 관성 좌표계에서 성립합니다.

---

### 본디의 $$k$$-인자

세 관찰자 $$O,O',O''$$이 1차원 상에서 운동하고 있다고 해봅시다.
여기서 관찰자 $$O$$에 대해 관찰자 $$O'$$이 일정한 속도로 운동하고 있다고 해봅시다.
그리고 또 다른 관찰자 $$O''$$은 관찰자 $$O$$에 대해 다른 위치에서 정지 상태라고 해봅시다.
관찰자 $$O$$가 $$t$$의 시간 간격으로 두 관찰자에게 빛 신호를 보낸다고 해봅시다.
관찰자 $$O''$$는 다음과 같이 동일한 시간 간격 $$t$$마다 신호를 받습니다.
하지만 관찰자 $$O'$$은 다음과 같이 조금 길어진 시간 간격마다 신호를 받습니다.
이 간격은 빠르게 운동할수록 더 커집니다.
변환된 시간 $$t'$$은 위 그림으로부터 $$t$$에 대해 선형적임을 알 수 있습니다.

$$
t'=kt
$$

이를 **본디의 $$k$$-인자(Bondi's $$k$$-Factor)**라고 합니다.
이 인자는 두 관찰자의 상대 속도에만 의존하는 양입니다.

---

## 시간 지연

다음과 같이 관찰자 $$O'$$가 관찰자 $$O$$에 대해 일정한 속도로 운동하고 있다고 해봅시다.
편의상 두 관찰자가 만나는 시점에 각자의 시계의 영점을 맞췄다고 해봅시다.
이제 관찰자 $$O$$가 시각 $$t$$에서 관찰자 $$O'$$에게 빛 신호를 보내는 상황을 생각해봅시다.
이 신호는 관찰자 $$O'$$의 입장에서 시각 $$t'$$에 도달합니다.
이를 사건 $$B$$라고 해봅시다.
두 양은 다음의 관계에 있습니다.

$$
t'=kt
$$

그리고 다시 관찰자 $$O$$에게 빛을 반사했다고 해봅시다.
이 빛은 앞선 관계에 따라 관찰자 $$O$$의 입장에서 $$kt'$$때 도달합니다.
이는 다음과 같이 쓸 수 있습니다.

$$
kt'=k^2t
$$

$$O$$의 입장에서 사건 $$B$$의 시간은 동시성의 레이더 정의에 따라 빛을 보낸 시각과 받은 시각의 중간 시점이므로 다음과 같습니다.

$$
t_B=\frac{1}{2}\left(t+k^2t\right)
$$

사건 $$B$$의 위치는 빛 신호가 이동한 시간에 광속을 곱하면 됩니다.
따라서 다음과 같습니다.

$$
\begin{align*}
x_B&=c\left(t_B-t\right)\\
&=\frac{1}{2}c\left(k^2-1\right)t
	\end{align*}
$$

관찰자 $$O'$$의 속도는 다음과 같이 구할 수 있습니다.

$$
	\begin{align*}
u&=\frac{x_B}{t_B}\\
&=\frac{c\left(k^2-1\right)}{k^2+1}
	\end{align*}
$$

$$k$$는 다음과 같습니다.

$$
k=\sqrt{\frac{c+u}{c-u}}
$$

특수 상대성 이론에서는 속도 $$u$$ 이외에도 광속에 대한 비인 다음의 양을 쓰기도 합니다.

$$
\beta=\frac{u}{c}
$$

이를 이용하면 다음과 같습니다.

$$
k=\sqrt{\frac{1+\beta}{1-\beta}}
$$

이제 각 관찰자가 측정한 사건 $$B$$의 시각을 생각해봅시다.
두 양의 비는 다음과 같습니다.

$$
	\begin{align*}
\frac{t_B}{t_B'}&=\frac{\left(k^2+1\right)t}{2kt}\\
&=\frac{1}{\sqrt{1-\beta^2}}\\
&=\gamma
	\end{align*}
$$

로런츠 인자가 도출되었습니다.
이는 $$1$$보다 큰 양입니다.
따라서 관찰자 $$O$$가 측정한 시간이 관찰자 $$O'$$이 측정한 시간보다 크다는 것을 알 수 있습니다.
단순히 그래프 상으로는 대소 관계가 반대로 보이지만 계산 결과는 그렇지 않습니다.
이 현상을 **시간 지연(Time Dilation)**이라고 합니다.

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
			u&1
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

어떤 입자가 관찰자 $$O$$에 대해 $$+x$$방향으로 일정한 속력 $$v$$로 운동한다고 해봅시다.
고전 역학에서는 관찰자 $$O'$$가 측정한 입자의 속도는 $$u-v$$입니다.
하지만 특수 상대성 이론에서는 다릅니다.
입자가 $$x(0)=a$$에서 출발할 때, 이 입자의 궤적은 다음과 같습니다.

$$
x=vt+a
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
	vt+a
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
	vdt
	\end{bmatrix}
$$

식을 전개하면 다음과 같습니다.

$$
\begin{cases}
	cdt'=\gamma\left(c-\beta v\right)dt\\
	dx'=\gamma\left(-\beta c+v\right)dt
\end{cases}
$$

따라서 관찰자 $$O'$$에 대한 입자의 속도는 다음과 같습니다.

$$
\begin{align*}
w&=\frac{dx'}{dt'}\\
&=\frac{u-v}{1-\displaystyle\frac{uv}{c^2}}
\end{align*}
$$

이 값 또한 $$c$$보다 커지지 않습니다.
극한 $$c\rightarrow\infty$$를 취하면 고전 역학에서의 상대 속도 식이 됩니다.

$$
\begin{align*}
\lim_{c\rightarrow\infty}w&=\lim_{c\rightarrow\infty}\frac{u-v}{1-\displaystyle\frac{uv}{c^2}}\\
&=u-v
\end{align*}
$$

---

## 길이 수축

이제 다음과 같이 어느 막대가 $$x'$$축 상의 $$x'=0$$과 $$x'=L$$를 양 끝으로 관찰자 $$O'$$에 대해 정지 상태라고 해봅시다.
관찰자 $$O'$$가 막대의 길이를 측정하기 위해 $$x'=0$$에서 막대의 반대편 끝으로 빛 신호를 보냈다고 해봅시다.
빛 신호가 막대의 끝에 도달한 사건을 사건 $$A$$라고 하고, 동시에 $$x'=0$$에서 사건 $$E$$가 발생한다고 해봅시다.
길이는 양 끝의 위치를 동시에 측정해야 하므로 관찰자 $$O'$$의 입장에서는 사건 $$A$$와 사건 $$E$$ 사이의 거리가 바로 막대의 길이입니다.
두 세계선은 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
	\begin{bmatrix}
		ct'\\
		L
	\end{bmatrix}\\
	\begin{bmatrix}
		ct'\\
		0
	\end{bmatrix}
\end{cases}
$$

관찰자 $$O$$의 입장에서는 사건 $$A$$와 사건 $$E$$가 동시에 발생하지 않습니다.
관찰자 $$O$$의 입장에서 막대의 길이가 어떻게 되는지 생각해봅시다.
사건 $$E$$와 동시에 발생하는 사건 $$B$$가 있다고 해봅시다.
이 또한 이전과 같이 $$x=0$$에서 막대의 반대편 끝으로 빛 신호를 보냈을 때, 빛 신호가 도달한 사건이라고 해봅시다.
사건 $$B$$의 좌표를 알아낸다면, 관찰자 $$O$$가 측정한 길이를 구할 수 있습니다.
두 세계선에 로런츠 변환을 취하면 다음과 같습니다.

$$
\begin{cases}
	\begin{bmatrix}
		ct\\
		x
	\end{bmatrix}=\begin{bmatrix}
		1&\beta\\
		\beta&1
	\end{bmatrix}\begin{bmatrix}
		ct'\\
		L
	\end{bmatrix}=\begin{bmatrix}
		ct'+\beta L\\
		ut'+L
	\end{bmatrix}\\
	\begin{bmatrix}
	ct\\
	x
	\end{bmatrix}=\begin{bmatrix}
	1&\beta\\
	\beta&1
	\end{bmatrix}\begin{bmatrix}
	ct'\\
	0
	\end{bmatrix}=\begin{bmatrix}
	ct'\\
	ut'
	\end{bmatrix}
\end{cases}
$$

사건 $$E$$의 좌표가 $$t=x=0$$이라고 해봅시다.
그렇다면 사건 $$B$$의 시각 또한 $$t=0$$이어야 합니다.
따라서 다음과 같습니다.

$$
\begin{align*}
&ct'+\beta L=0\\
&\rightarrow t'=-\frac{\beta L}{c}
\end{align*}
$$

이때 사건 $$B$$의 $$x$$좌표는 다음과 같습니다.

$$
\begin{align*}
x_B&=\gamma\left(-\beta^2L+L\right)\\
&=\frac{L}{\gamma}
\end{align*}
$$

기존의 길이에 비해 $$\displaystyle\frac{1}{\gamma}$$가 되어 줄어들었습니다.
이 현상을 **길이 수축(Length Contraction)**이라고 합니다.

---

## 로런츠 변환의 합성

로런츠 변환을 두 번 하는 경우에 대해 생각해봅시다.
다음의 두 로런츠 변환을 생각해봅시다.

$$
\begin{cases}
	\mathbf{L}_u=\gamma_u\begin{bmatrix}
		1&\beta_u\\
		\beta_u&1
	\end{bmatrix}\\
	\mathbf{L}_v=\gamma_v\begin{bmatrix}
		1&\beta_v\\
		\beta_v&1
	\end{bmatrix}
\end{cases}
$$

변환 $$\mathbf{L}_u$$을 한 뒤에 변환 $$\mathbf{L}_v$$를 한다면 합성 변환 $$\mathbf{L}_w$$는 다음과 같습니다.

$$
\begin{align*}
\mathbf{L}_w&=\mathbf{L}_u\mathbf{L}_v\\
&=\gamma_v\begin{bmatrix}
	1&\beta_v\\
	\beta_v&1
\end{bmatrix}\gamma_u\begin{bmatrix}
1&\beta_u\\
\beta_u&1
\end{bmatrix}\\
&=\gamma_u\gamma_v\begin{bmatrix}
	1+\beta_u\beta_v&\beta_u+\beta_v\\
	\beta_u+\beta_v&1+\beta_u\beta_v\\
\end{bmatrix}\\
	&=\gamma_u\gamma_v\left(1+\beta_u\beta_v\right)\begin{bmatrix}
		1&\displaystyle\frac{\beta_u+\beta_v}{1+\beta_u\beta_v}\\
		\displaystyle\frac{\beta_u+\beta_v}{1+\beta_u\beta_v}&1
	\end{bmatrix}\\
	&=\gamma_u\gamma_v\left(1+\beta_u\beta_v\right)\begin{bmatrix}
		1&\displaystyle\frac{1}{c}\displaystyle\frac{u+v}{1+\displaystyle\frac{uv}{c^2}}\\
		\displaystyle\frac{1}{c}\displaystyle\frac{u+v}{1+\displaystyle\frac{uv}{c^2}}&1
	\end{bmatrix}
\end{align*}
$$

$$\gamma_u\gamma_v\left(1+\beta_u\beta_v\right)$$는 다음과 같이 계산됩니다.

$$
\begin{align*}
\gamma_u\gamma_v\left(1+\beta_u\beta_v\right)&=\frac{1}{\sqrt{1-\beta_u^2}}\frac{1}{\sqrt{1-\beta_v^2}}\left(1+\beta_u\beta_v\right)\\
&=\frac{1+\beta_u\beta_v}{\sqrt{1+\beta_u^2\beta_v^2-\beta_u^2-\beta_v^2}}\\
&=\frac{1}{\sqrt{\displaystyle\frac{1+\beta_u^2\beta_v^2-\beta_u^2-\beta_v^2}{1+\beta_u^2\beta_v^2+2\beta_u\beta_v}}}\\
&=\frac{1}{\sqrt{\displaystyle\frac{1+\beta_u^2\beta_v^2+2\beta_u\beta_v-\beta_u^2-2\beta_u\beta_v-\beta_v^2}{1+\beta_u^2\beta_v^2+2\beta_u\beta_v}}}\\
&=\frac{1}{\sqrt{1-\displaystyle\frac{\beta_u^2+2\beta_u\beta_v+\beta_v^2}{1+\beta_u^2\beta_v^2+2\beta_u\beta_v}}}\\
&=\frac{1}{\sqrt{1-\displaystyle\frac{\left(\beta_u+\beta_v\right)^2}{\left(1+\beta_u\beta_v\right)^2}}}\\
&=\frac{1}{\sqrt{1-\left(\displaystyle\frac{1}{c}\displaystyle\frac{u+v}{1+\displaystyle\frac{uv}{c^2}}\right)^2}}
\end{align*}
$$

합성 변환을 다음과 같이 쓸 수 있습니다.

$$
\begin{align*}
\mathbf{L}_w=\frac{1}{\sqrt{1-\left(\displaystyle\frac{1}{c}\displaystyle\frac{u+v}{1+\displaystyle\frac{uv}{c^2}}\right)^2}}\begin{bmatrix}
	1&\displaystyle\frac{1}{c}\displaystyle\frac{u+v}{1+\displaystyle\frac{uv}{c^2}}\\
	\displaystyle\frac{1}{c}\displaystyle\frac{u+v}{1+\displaystyle\frac{uv}{c^2}}&1
\end{bmatrix}
\end{align*}
$$

식을 살펴보면 속도 변환 식이 있는 것을 알 수 있습니다.

$$
w=\frac{u+v}{1+\frac{uv}{c^2}}
$$

따라서 합성 변환은 다음과 같습니다.

$$
\begin{align*}
\mathbf{L}_w=\gamma_w\begin{bmatrix}
	1&\beta_w\\
	\beta_w&1
\end{bmatrix}\ \ \ \text{where }\gamma_w=\frac{1}{\sqrt{1-\beta_w^2}}
\end{align*}
$$

---

## 신속도

$$\beta$$와 $$k$$의 관계식을 다시 살펴봅시다.

$$
\begin{align*}
\beta=\frac{k-k^{-1}}{k+k^{-1}}
\end{align*}
$$

이는 자연로그를 이용하여 다음과 같이 나타낼 수 있습니다.

$$
\begin{align*}
&k=e^{\ln k}\\
&\beta=\frac{e^{\ln k}-e^{-\ln k}}{e^{\ln k}+e^{-\ln k}}=\tanh\left(\ln k\right)
\end{align*}
$$

여기서 $$\ln k$$를 다음과 같다고 해봅시다.

$$
\phi=\ln k
$$

로런츠 변환을 다시 살펴봅시다.

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

$$\beta$$만을 이용하여 표현하면 다음과 같습니다.

$$
\begin{bmatrix}
	ct\\
	x
\end{bmatrix}=\begin{bmatrix}
\displaystyle\frac{1}{\sqrt{1-\beta^2}}&\displaystyle\frac{\beta}{\sqrt{1-\beta^2}}\\
\displaystyle\frac{\beta}{\sqrt{1-\beta^2}}&\displaystyle\frac{1}{\sqrt{1-\beta^2}}
\end{bmatrix}\begin{bmatrix}
ct'\\
x'
\end{bmatrix}
$$

이전에 정의한 양 $$\phi$$를 이용하면 다음과 같이 나타낼 수 있습니다.

$$
\begin{align*}
&\beta=\tanh\phi\\
&\begin{bmatrix}
	ct\\
	x
\end{bmatrix}=\begin{bmatrix}
\displaystyle\frac{1}{\sqrt{1-\tanh\phi^2}}&\displaystyle\frac{\tanh\phi}{\sqrt{1-\tanh\phi^2}}\\
\displaystyle\frac{\tanh\phi}{\sqrt{1-\tanh\phi^2}}&\displaystyle\frac{1}{\sqrt{1-\tanh\phi^2}}
\end{bmatrix}\begin{bmatrix}
ct'\\
x'
\end{bmatrix}
\end{align*}
$$

식을 정리하면 다음과 같습니다.

$$
\begin{bmatrix}
	ct\\
	x
\end{bmatrix}=\begin{bmatrix}
\cosh\phi&\sinh\phi\\
\sinh\phi&\cosh\phi
\end{bmatrix}\begin{bmatrix}
ct'\\
x'
\end{bmatrix}
$$

유클리드 공간의 회전 변환과 비슷한 형태입니다.
단지 삼각 함수가 아닌 쌍곡선 함수로 표현됩니다.
이런 변환을 **쌍곡 회전 변환(Hyperbolic Rotational Transformation)**이라고 합니다.
그리고 이전에 정의한 $$\phi$$는 변환의 **신속도(Rapidity)**라고 하며, 이 회전 변환에서 회전 각을 의미합니다.

### 속도 변환

신속도를 이용하면 속도 변환 식이 더 간단해집니다.
속도 변환 식을 다시 살펴봅시다.

$$
w=\frac{u+v}{1+\frac{uv}{c^2}}
$$

$$\beta$$를 이용하여 표현하면 다음과 같습니다.

$$
\beta_w=\frac{\beta_u+\beta_v}{1+\beta_u\beta_v}
$$

신속도를 이용하여 표현해봅시다.

$$
\begin{align*}
\tanh\phi_w&=\frac{\tanh\phi_u+\tanh\phi_v}{1+\tanh\phi_u\tanh\phi_v}\\
&=\tanh\left(\phi_u+\phi_v\right)
\end{align*}
$$

따라서 다음과 같습니다.

$$
\phi_w=\phi_u+\phi_v
$$

신속도를 이용하면 속도 변환 식이 간단하게 합으로 나타납니다.

---

## 로런츠 군과 푸앵카레 군

이러한 2차원 로런츠 변환들은 **로런츠 군(Lorentz Group)**을 형성합니다.

### 군

먼저 **군(Group)**에 대해 간단히 짚고 넘어갑시다.
군은 대상들의 집합과 그 위에 정의된 연산이 다음의 네 가지 공리를 만족하는 구조입니다.

- 닫힘성: 대상들의 연산 결과가 군에 속해 있어야 합니다.

$$
\forall a,b\in G,a\cdot b\in G
$$

- 결합 법칙: 세 대상들의 연산의 순서를 바꿔도 결과가 같아야 합니다.

$$
\forall a,b,c\in G,\left(a\cdot b\right)\cdot c=a\cdot\left(b\cdot c\right)
$$

- 항등원: 어떤 대상과 연산을 하면 결과가 연산 전과 같습니다.

$$
\exists e\in G,\forall a\in G,a\cdot e=e\cdot a=a
$$

- 역원: 어떤 대상과 연산을 하면 항등원이 나옵니다.

$$
\forall a\in G,\exists a^{-1},a\cdot a^{-1}=a^{-1}\cdot a=a
$$

이러한 군을 다음과 같이 표기합니다.

$$
\left(G,\cdot\right)
$$

$$G$$는 대상들의 집합입니다.
$$\cdot$$은 이항 연산입니다.

$$
\cdot:G\times G\rightarrow G
$$

### 로런츠 군

로런츠 군은 다음과 같이 나뉩니다.

- 고유 정시적(Proper Orthochronous): 공간 반전과 시간 역전이 없습니다.
- 고유적(Proper): 공간 반전이 없습니다.
- 정시적(Orthochronous): 시간 역전이 없습니다.
- 그 외: 공간 반전과 시간 역전을 포함합니다.

공간 반전은 다음과 같이 표현합니다.

$$
\begin{bmatrix}
	ct\\
	x
\end{bmatrix}\mapsto\begin{bmatrix}
ct'\\
x'
\end{bmatrix}=\begin{bmatrix}
ct\\
-x
\end{bmatrix}
$$

시간 역전은 다음과 같이 표현합니다.

$$
\begin{bmatrix}
	ct\\
	x
\end{bmatrix}\mapsto\begin{bmatrix}
ct'\\
x'
\end{bmatrix}=\begin{bmatrix}
-ct\\
x
\end{bmatrix}
$$

이 두 성질을 갖지 않는 로런츠 군을 **고유 정시적 로런츠 군(Proper Orthochronous Lorentz Group)**이라고 합니다.

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
하나는 사건 $$A$$로부터 광자가 출발했을 때 광자가 도달할 수 있는 모든 '미래'의 영역인 **미래 광추(Future Light Cone)**입니다.
광자는 사건 $$A$$로부터 미래 광추의 임의의 위치로 나아갈 수 있습니다.

(light cone)

사건 $$A$$로부터 출발하는 순간, $$t>0$$이 되므로 미래의 영역입니다.

(light cone)

또 다른 하나는 광자가 사건 $$A$$에 도달했을 때 광자가 지나올 수 있는 모든 '과거'의 영역인 **과거 광추(Past Light Cone)**입니다.
광자는 과거 광추의 임의의 위치로부터 사건 $$A$$에 도달할 수 있습니다.

(light cone)

사건 $$A$$에 도달하기 전에는 $$t<0$$이므로 과거의 영역입니다.

(light cone)

광추는 원점으로부터 시간에 따라 광속 $$c$$로 퍼집니다.
즉, 구형의 파면을 형성하게 됩니다.

이 광추는 관성 좌표계와 상관 없이 특정 사건에 대해서는 구조가 동일합니다.
즉, 시공간에서 불변의 구조입니다.
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

두 사건이 광자의 세계선 위에 위치한다면, 다음과 같이 쓸 수 있습니다.

$$
\begin{align*}
	&ct=\sqrt{\left(x_2-x_1\right)^2+\left(y_2-y_1\right)^2+\left(z_2-z_1\right)^2}\\
&\rightarrow c^2\left(t_2-t_1\right)^2-\left(x_2-x_1\right)^2-\left(y_2-y_1\right)^2-\left(z_2-z_1\right)^2=0
\end{align*}
$$

빛은 관성 좌표계와 상관 없이 동일한 시간에 동일한 거리만큼 나아갑니다.
따라서 이러한 두 사건은 관성 좌표계와는 상관 없이 같은 형식으로 나타낼 수 있습니다.

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

### 표준 로런츠 변환

앞서 언급한 관계식을 통해 로런츠 변환 행렬의 모든 성분을 알아내봅시다.

$$
\mathbf{L}^T\mathbf{g}\mathbf{L}=\mathbf{g}
$$

2차원 로런츠 변환을 통해 $$L_{00},L_{01},L_{10},L_{11}$$은 이미 구했습니다.

$$
\mathbf{L}=\begin{bmatrix}
	\gamma&\gamma\beta&L_{02}&L_{03}\\
	\gamma\beta&\gamma&L_{12}&L_{13}\\
	L_{20}&L_{21}&L_{22}&L_{23}\\
	L_{30}&L_{31}&L_{32}&L_{33}
\end{bmatrix}
$$

따라서 다음과 같이 쓸 수 있습니다.

$$
	\begin{bmatrix}
		\gamma&\gamma\beta&L_{20}&L_{30}\\
		\gamma\beta&\gamma&L_{21}&L_{31}\\
		L_{02}&L_{12}&L_{22}&L_{32}\\
		L_{03}&L_{13}&L_{23}&L_{33}
	\end{bmatrix}
	\begin{bmatrix}
		1&0&0&0\\
		0&-1&0&0\\
		0&0&-1&0\\
		0&0&0&-1
	\end{bmatrix}
\begin{bmatrix}
	\gamma&\gamma\beta&L_{02}&L_{03}\\
	\gamma\beta&\gamma&L_{12}&L_{13}\\
	L_{20}&L_{21}&L_{22}&L_{23}\\
	L_{30}&L_{31}&L_{32}&L_{33}
\end{bmatrix}=	\begin{bmatrix}
1&0&0&0\\
0&-1&0&0\\
0&0&-1&0\\
0&0&0&-1
\end{bmatrix}
$$

$$00$$번째 성분과 $$11$$번째 성분만 비교하면 다음과 같습니다.

$$
	\begin{cases}
	00:\gamma^2-\gamma^2\beta^2-L_{20}^2-L_{30}^2=1\\
	11:\gamma^2\beta^2-\gamma^2-L_{21}^2-L_{31}^2=-1
\end{cases}
$$

여기서 $$\gamma^2-\gamma^2\beta^2=1$$이므로 다음과 같습니다.

$$
	\begin{cases}
	00:L_{20}^2+L_{30}^2=0\\
	11:L_{21}^2+L_{31}^2=0
\end{cases}
$$

따라서 위 네 성분은 모두 $$0$$입니다.
다음으로 $$02,03,12,13$$번째 성분을 비교하면 다음과 같습니다.

$$
	\begin{cases}
	02:\gamma L_{02}-\gamma\beta L_{12}=0\\
	03:\gamma L_{03}-\gamma\beta L_{13}=0\\
	12:\gamma\beta L_{02}-\gamma L_{12}=0\\
	13:\gamma\beta L_{03}-\gamma L_{13}=0
\end{cases}
$$

$$\gamma\neq0$$이고, $$\beta\neq1$$이므로 위 네 성분 또한 모두 $$0$$입니다.
마지막으로 $$22,23,32,33$$번째 성분을 살펴봅시다.

$$
	\begin{cases}
	22:-L_{22}^2-L_{32}^2=-1\\
	23:-L_{22}L_{23}-L_{32}L_{33}=0\\
	32:-L_{22}L_{23}-L_{32}L_{33}=0\\
	33:-L_{23}^2-L_{33}^2=-1
\end{cases}
$$

이 성분들을 알아내기 전에 다음 행렬에 대해 살펴봅시다.

$$
\mathbf{L}_{sub}=\begin{bmatrix}
	L_{22}&L_{23}\\
	L_{32}&L_{33}
\end{bmatrix}
$$

이 행렬과 전치 행렬의 곱은 다음과 같습니다.

$$
\begin{align*}
\mathbf{L}_{sub}^T\mathbf{L}_{sub}&=\begin{bmatrix}
	L_{22}&L_{32}\\
	L_{23}&L_{33}
\end{bmatrix}\begin{bmatrix}
	L_{22}&L_{23}\\
	L_{32}&L_{33}
\end{bmatrix}\\
&=\begin{bmatrix}
	L_{22}^2+L_{32}^2&L_{23}L_{23}+L_{32}L_{33}\\
	L_{22}L_{23}+L_{32}L_{33}&L_{23}^2+L_{33}^2
\end{bmatrix}
\end{align*}
$$

이전에 구한 성분 관계식을 이용하면 다음과 같습니다.

$$
\mathbf{L}_{sub}^T\mathbf{L}_{sub}=\begin{bmatrix}
	1&0\\
	0&1
\end{bmatrix}
$$

즉, $$\mathbf{L}_{sub}^T=\mathbf{L}_{sub}^{-1}$$이고, $$\mathbf{L}_{sub}$$는 직교 행렬입니다.

다시 다음의 관계식을 살펴봅시다.

$$
\mathbf{L}^T\mathbf{g}\mathbf{L}=\mathbf{g}
$$

$$\mathbf{L}$$의 행렬식을 구하면 다음과 같습니다.

$$
\begin{align*}
&\det(\mathbf{L})^2\det\left(\mathbf{g}\right)=\det\left(\mathbf{g}\right)\\
&\det\left(\mathbf{L}\right)=\pm1
\end{align*}
$$

여기서 고유 로런츠 변환은 공간의 반전이 없어야 하므로 다음의 조건이 필요합니다.

$$
\det\left(\mathbf{L}\right)=1
$$

이러면 $$\mathbf{L}_{sub}$$는 $$y,z$$축의 회전 변환을 나타냅니다.
표준 로런츠 변환은 두 축이 회전을 하지 않은 상태를 의미하므로 다음과 같습니다.

$$
\mathbf{L}_{sub}=\begin{bmatrix}
	1&0\\
	0&1
\end{bmatrix}
$$

따라서 표준 로런츠 변환 행렬은 다음과 같습니다.

$$
\mathbf{L}=\begin{bmatrix}
	\gamma&\gamma\beta&0&0\\
	\gamma\beta&\gamma&0&0\\
	0&0&1&0\\
	0&0&0&1
\end{bmatrix}
$$

### 고유 정시적 로런츠 변환

지금까지는 부스트가 $$+x$$방향이고, 모든 축의 방향이 같은 로런츠 변환에 대해 알아봤습니다.
이제 일반적인 상황을 생각해봅시다.
축의 방향이 모두 다르면서, 부스트의 방향도 정해지지 않았습니다.
물론 공간 반전과 시간 역전은 포함하지 않습니다.
일반적인 로런츠 변환은 다음과 같은 형태로 나타납니다.

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
\end{bmatrix}\ \ \ \text{where }\mathbf{L}=\begin{bmatrix}
1&0\\
0&\mathbf{H}
\end{bmatrix}\mathbf{L}_u\begin{bmatrix}
1&0\\
0&\mathbf{K}^T
\end{bmatrix}
$$

여기서 $$\mathbf{H},\mathbf{K}$$는 고유 직교 행렬이고, $$\mathbf{L}_u$$는 표준 로런츠 변환입니다.
앞서 언급했듯이 부스트의 방향이 정해지지 않았습니다.
하지만 우리는 그동안 $$+x$$방향 부스트에 대해 고려했습니다.
따라서 $$+x$$방향 부스트라고 가정을 한 뒤, 회전 변환 $$\mathbf{K}$$를 통해 $$x'-y'-z'$$축을 부스트의 방향과 일치시킵니다.
다음으로 표준 로런츠 변환을 통해 $$+x$$방향으로 부스트를 해줍니다.
마지막으로 회전된 축들을 원하는 방향인 $$x-y-z$$으로 정렬하기 위해 다시 한 번 회전 변환을 합니다.
일반적인 로런츠 변환은 이런 과정을 통해 유도되었고, 이를 $$고유 정시적 로런츠 변환(Proper Orthochronous Lorentz Transformation)**이라고 합니다.
이런 변환들은 다음의 성질을 가집니다.

- $$\mathbf{L}$$은 유사 직교적입니다: $$\mathbf{L}^{-1}=\mathbf{g}\mathbf{L}^T\mathbf{g}$$
- $$\mathbf{H}$$의 $$00$$번째 성분은 양수입니다: 시간 역전이 없음을 의미합니다.
- $$\det(\mathbf{L})=1: 공간 반전이 없음을 의미합니다.

일반적인 로런츠 변환은 첫번째 성질만을 만족합니다.
두번째 성질을 만족하는 변환은 정시적 로런츠 변환입니다.
세번째 성질을 만족하는 변환은 고유 로런츠 변환입니다.

마지막으로 공간 상의 병진 이동까지 포함시키면 다음과 같이 표현할 수 있습니다.

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

이런 로런츠 변환을 **비동차 로런츠 변환(Inhomogeneous Lorentz Transformation)** 또는 **푸앵카레 변환(Poincaré Transformation)**이라고 합니다.
각 성분을 다음과 같이 써봅시다.

$$
\begin{bmatrix}
	x^0\\
	x^1\\
	x^2\\
	x^3
\end{bmatrix}=\begin{bmatrix}
ct\\
x\\
y\\
z
\end{bmatrix}
$$

위 첨자는 제곱이 아니라 인덱스를 의미합니다.
따라서 각 성분을 다음과 같이 쓸 수 있습니다.

$$
	x^a=\sum_{b=0}^3{L^a}_bx'^b+C^a\ \ \ (a=0,1,2,3)
$$

혹은 아인슈타인 표기법에 따라 합의 기호를 생략할 수 있습니다.

$$
x^a={L^a}_bx'^b+C^a
$$

---

## 시공간의 구조

이제 이 시공간을 어떻게 기술하는지 설명하겠습니다.

### $$4$$-벡터

앞서 로런츠 변환은 $$4$$차원 회전 변환임을 설명했습니다.
먼저 $$3$$차원 유클리드 공간의 회전은 다음과 같이 기술됩니다.

$$
\begin{bmatrix}
	X^1\\
	X^2\\
	X^3
\end{bmatrix}=\mathbf{H}\begin{bmatrix}
X'^1\\
X'^2\\
X'^3
\end{bmatrix}
$$

시공간을 기술할 때에는 이런 공간 성분에 이어 시간 성분까지 포함시킨 $$4-벡터(Four-Vector)$$를 이용합니다.
$$4$$-벡터와 로런츠 변환을 이용하여 기술한 변환 식은 다음과 같습니다.

$$
\begin{bmatrix}
	X^0\\
	X^1\\
	X^2\\
	X^3
\end{bmatrix}=\mathbf{L}\begin{bmatrix}
X'^0\\
X'^1\\
X'^2\\
X'^3
\end{bmatrix}
$$

$$4$$-벡터는 두 사건 사이의 변위를 의미하므로 병진 이동이 포함되지 않습니다.

### 시간 성분과 공간 성분

### 내적

$$4$$-벡터 간의 내적은 다음과 같이 정의됩니다.

$$
g(X,Y)=g_{ab}X^aY^b
$$

현재 다루는 시공간의 경우는 다음과 같습니다.

$$
g(X,Y)=X^0Y^0-X^1Y^1-X^2Y^2-X^3Y^3
$$

혹은 다음과 같이 인덱스의 위치를 바꾸어 표기하는 방법도 있습니다.

$$
	\begin{align*}
&X_a=g_{ab}X^b\\
&\rightarrow g(X,Y)=X_aY^a=X_0Y^0+X_1Y^1+X_2Y^2+X_3Y^3
	\end{align*}
$$

### $$4$$-벡터의 분류

$$4$$-벡터는 다음 세 가지로 분류됩니다.

- $$g(X,X)>0$$: **시간같은(Timelike)** 벡터
- $$g(X,X)<0$$: **공간같은(Spacelike)** 벡터
- $$g(X,X)=0$$: **널(Null)** 벡터 혹은 **빛같은(Lightlike)** 벡터

시간같은 벡터의 경우, 모든 공간 성분이 $$0$$이 되는 관성 좌표계가 존재합니다.
즉, 두 사건이 발생하는 장소가 동일한 관성 좌표계가 존재한다는 의미입니다.
공간같은 벡터의 경우, 시간 성분이 $$0$$이 되는 관성 좌표계가 존재합니다.
즉, 두 사건이 동시에 발생한다고 관측되는 관성 좌표계가 존재합니다.

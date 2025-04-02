컨버터의 소신호 모델
=

---

## 목차
- [소신호 모델링](#소신호-모델링)
- [선형화](#선형화)
- [PWM 스위치의 소신호 모델](#PWM-스위치의-소신호-모델)
- [비절연형 컨버터의 소신호 모델](#비절연형-컨버터의-소신호-모델)

---

## 소신호 모델링

선형 제어론을 통해 컨버터의 제어기를 설계하려면 컨버터를 LTI 시스템으로 바꿔야합니다.
첫번째 과정은 평균화고, 두번째 과정은 **소신호 모델링(Small-Signal Modeling)**입니다.
소신호 모델링은 특정 동작점에 대해 선형화를 하여 컨버터를 LTI 시스템으로 바꾸는 과정입니다.
LTI 시스템으로 바꾼 후에는 선형 제어론을 이용하여 컨버터의 제어기를 설계할 수 있습니다.

---

## 선형화

선형화를 모든 동작점에 대해 하는 것은 가능하지만, 그만큼 제어기의 설계가 까다로워집니다.
따라서 보통 **최악의 경우에 대해 설계(Worst Case Design)**를 진행합니다.
그러면 다른 경우에 대해서는 정상 동작을 하게 됩니다.
이제 선형화를 어떤 과정을 통해 하는지 설명하겠습니다.

### 테일러 급수

다음의 함수 $$y=f(x)$$를 생각해봅시다.

$$
f:\mathbb{R}\rightarrow\mathbb{R}
$$

(y=f(x))

그리고 다음과 같이 동작점 $$\left(X,f(X)\right)$$에서 소신호 $$\hat{x}$$를 가했다고 해봅시다.

$$
x=X+\hat{x}
$$

여기서 소신호는 $$1$$에 비해 매우 작다고 가정합니다.
이때 함수 $$f$$의 테일러 전개는 다음과 같습니다.

$$
	\begin{align*}
		f(x)&=f(X+\hat{x})\\
		&=\frac{1}{0!}f(X)+\frac{1}{1!}\frac{df}{dx}\Big\vert_{x=X}\left(x-X\right)+\frac{1}{2!}\frac{d^2f}{dx^2}\Big\vert_{x=X}\left(x-X\right)+\cdots\\
		&=f(X)+\frac{df}{dx}\Big\vert_{x=X}\left(x-X\right)+\frac{1}{2}\frac{d^2f}{dx^2}\Big\vert_{x=X}\left(x-X\right)+\cdots\\
		&=f(X)+\frac{df}{dx}\Big\vert_{x=X}\hat{x}+\frac{1}{2}\frac{d^2f}{dx^2}\Big\vert_{x=X}\hat{x}+\cdots
		\end{align*}
$$

출력 신호를 $$y=Y+\hat{y}$$와 같이 표현하면 다음과 같습니다.

$$
Y+\hat{y}=f(X)+\frac{df}{dx}\Big\vert_{x=X}\hat{x}+\frac{1}{2}\frac{d^2f}{dx^2}\Big\vert_{x=X}\hat{x}+\cdots
$$

여기서 $$Y,f(X)$$는 dc 항이고, $$2$$차 이상의 항은 매우 작아서 무시할 수 있습니다.
따라서 **소신호 모델(Small-Signal Model)**에 대한 식은 다음과 같습니다.

$$
\begin{align*}
		&\hat{y}=\frac{df}{dx}\Big\vert_{x=X}\hat{x}\\
		&\frac{\hat{y}}{\hat{x}}=\frac{df}{dx}\Big\vert_{x=X}
		\end{align*}
$$

혹은 **소신호 이득(Small-Signal Gain)**이라고 합니다.

---

## PWM 스위치의 소신호 모델

PWM 스위치의 평균화 모델을 떠올려 봅시다.

(PWM Switch)

$$
\begin{cases}
			\overline{v}_{cp}(t)=\overline{v}_{ap}(t)d(t)\\
			\overline{i}_{a}(t)=\overline{i}_{c}(t)d(t)
		\end{cases}
$$

각 변수를 동작점(dc)과 소신호로 표현하면 다음과 같습니다.

$$
\begin{cases}
			\overline{v}_{ap}=V_{ap}+\hat{v}_{ap}\\
			\overline{v}_{cp}=V_{cp}+\hat{v}_{cp}\\
			\overline{i}_{a}=I_{a}+\hat{i}_{a}\\
			\overline{i}_{c}=I_{c}+\hat{i}_{c}\\
   \overline{d}(t)=D+\hat{d}
		\end{cases}
$$

이 식을 평균화 모델 표현식에 대입하면 다음과 같습니다.

$$
\begin{cases}
			V_{cp}+\hat{v}_{cp}=\left(V_{ap}+\hat{v}_{ap}\right)\left(D+\hat{d}\right)\\
			I_{a}+\hat{i}_{a}=\left(I_{c}+\hat{i}_{c}\right)\left(D+\hat{d}\right)
		\end{cases}
$$

식을 전개하면 다음과 같습니다.

$$
\begin{cases}
			V_{cp}+\hat{v}_{cp}=DV_{ap}+\hat{d}V_{ap}+D\hat{v}_{ap}+\hat{d}\hat{v}_{ap}\\
			I_a+\hat{i}_a=DI_c+\hat{d}I_c+D\hat{i}_c+\hat{d}\hat{i}_c
		\end{cases}
$$

동작점끼리 곱해진 항은 dc 항이고, 소신호끼리 곱해진 항은 2차항으로 매우 작아서 무시할 수 있습니다.
따라서 PWM 스위치의 소신호 표현은 다음과 같습니다.

$$
\begin{cases}
			\hat{v}_{cp}=\hat{d}V_{ap}+D\hat{v}_{ap}\\
			\hat{i}_a=\hat{d}I_c+D\hat{i}_c
		\end{cases}
$$

이 관계식을 살펴보면 소신호 전압과 전류는 턴 비 $1:D$인 이상 변압기로 모델링할 수 있습니다.
소신호 듀티의 경우는 동작점과의 곱으로 나타납니다.
이는 종속 전압원과 종속 전류원으로 모델링할 수 있습니다.
PWM 스위치의 소신호 모델은 다음과 같습니다.

---

## 비절연형 컨버터의 소신호 모델

자세한 내용은 각 문서 참고 바랍니다.
- [벅 컨버터]
- [부스트 컨버터]
- [벅-부스트 컨버터]

### 벅 컨버터

벅 컨버터의 소신호 모델은 다음과 같습니다.

### 부스트 컨버터

부스트 컨버터의 소신호 모델은 다음과 같습니다.

### 벅-부스트 컨버터

벅-부스트 컨버터의 소신호 모델은 다음과 같습니다.

---

## 같이 보기

- [컨버터 모델링]()
- [컨버터의 평균화 모델]()
- [컨버터의 전달 함수]()

# 컨버터의 소신호 모델

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

그리고 다음과 같이 동작점 $$\left(X,Y\right)$$에서 소신호 $$\hat{x},\hat{y}$$만큼을 가했다고 해봅시다.

$$
\begin{align*}
		&x=X+\hat{x}\\
		&y=Y+\hat{y}
	\end{align*}
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

$$y=Y+\hat{y}$$를 이용하여 표현하면 다음과 같습니다.

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

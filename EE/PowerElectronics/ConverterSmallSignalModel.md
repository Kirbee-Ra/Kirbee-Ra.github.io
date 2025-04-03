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

<figure style="text-align: center;">
  <img src="./PEFigure/선형화 함수.png" alt="선형화 함수" width="80%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 함수 \(y=f(x)\))
  </figcaption>
</figure>

그리고 다음과 같이 동작점 $$\left(X,f(X)\right)$$에서 소신호 $$\hat{x}$$를 가했다고 해봅시다.

$$
x=X+\hat{x}
$$

<figure style="text-align: center;">
  <img src="./PEFigure/소신호 근사.png" alt="소신호 근사" width="80%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 함수의 선형 근사)
  </figcaption>
</figure>

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

<figure style="text-align: center;">
  <img src="./PEFigure/평균화 스위치.png" alt="PWM 스위치의 평균화 모델" width="80%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. PWM 스위치의 평균화 모델)
  </figcaption>
</figure>

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
   \overline{d}=D+\hat{d}
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
			V_{cp}+\hat{v}_{cp}=V_{ap}D+V_{ap}\hat{d}+\hat{v}_{ap}D+\hat{v}_{ap}\hat{d}\\
			I_a+\hat{i}_a=I_cD+I_c\hat{d}+\hat{i}_cD+\hat{i}_c\hat{d}
		\end{cases}
$$

동작점끼리 곱해진 항은 dc 항이고, 소신호끼리 곱해진 항은 2차항으로 매우 작아서 무시할 수 있습니다.
따라서 PWM 스위치의 소신호 표현은 다음과 같습니다.

$$
\begin{cases}
			\hat{v}_{cp}=V_{ap}\hat{d}+\hat{v}_{ap}D\\
			\hat{i}_a=I_c\hat{d}+\hat{i}_cD
		\end{cases}
$$

이 관계식을 살펴보면 소신호 전압과 전류는 턴 비가 $$1:D$$인 이상 변압기로 모델링할 수 있습니다.
소신호 듀티의 경우는 동작점과의 곱으로 나타납니다.
이는 종속 전압원과 종속 전류원으로 모델링할 수 있습니다.
PWM 스위치의 소신호 모델은 다음과 같습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/소신호 스위치.png" alt="PWM 스위치의 소신호 모델" width="80%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. PWM 스위치의 소신호 모델)
  </figcaption>
</figure>

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

## 컨버터의 전압 모드 제어

지금까지 봐온 소신호 모델은 개루프 컨버터에 대한 내용이었습니다.
이제 피드백 회로가 있는 폐루프 컨버터에 대해 설명하겠습니다.
다음은 가장 기본적인 **전압 모드 제어(Voltage Mode Control)**를 이용한 폐루프 컨버터입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/VMC 기본.png" alt="VMC 기본" width="80%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 컨버터의 전압 피드백 회로)
  </figcaption>
</figure>

회로를 보면 알 수 있듯이 출력 전압에 대한 정보를 받아서 다시 파워 스테이지에 수정된 값을 전송하는 구조입니다.
전압에 대한 정보만을 이용하기 때문에 전압 모드 제어라고 합니다.
제어 회로는 다음과 같이 전압 피드백 회로와 PWM 블록으로 구성됩니다.
각 부분에 대해 설명하겠습니다.

### 출력 전압 제어

먼저 전압 피드백 회로를 살펴봅시다.
Op-Amp의 두 단자는 가상 단락되어 있으므로 반전 단자에서 KCL을 적용하면 다음과 같습니다.

$$
\frac{V_{ref}-v_{ctrl}}{Z_2}+\frac{V_{ref}-v_o}{Z_1}+\frac{V_{ref}}{R_x}=0
$$

이 식은 다음과 같이 정리할 수 있습니다.

$$
V_{ref}-v_{ctrl}=\frac{Z_2}{Z_1}\left(v_o-V_{ref}\left(1+\frac{Z_1}{R_x}\right)\right)
$$

전압 제어가 완료되면 정상 상태로 진입합니다.
정상 상태에서는 시간에 의존하는 항이 $$0$$이 되고, dc 항만 남으므로 $$s=j0$$을 통해 계산합니다.
제어가 완료됐다는 것은 우변의 괄호 안에 있는 식이 다음과 같이 $$0$$이 됐다는 의미입니다.

$$
V_o-V_{ref}\left(1+\frac{\left\vert Z_1(j0)\right\vert}{R_x}=0
$$

하지만 좌변은 $$0$$이 아닌 상수입니다.
따라서 우변의 괄호 앞에 있는 계수의 크기가 정상 상태에서 무한대로 발산해야 합니다.

$$
\left\vert\frac{Z_2(j0)}{Z_1(j0)}\right\vert\rightarrow\infty
$$

따라서 정상 상태에서 출력 전압은 다음과 같습니다.

$$
V_o=V_{ref}\left(1+\frac{\left\vert Z_1(j0)\right\vert}{R_x}
$$

출력 전압이 $$Z_1,R_x$$에 의존하는 것을 알 수 있습니다.
여기서 제어기를 설계할 때 기억해야 할 두 가지를 알 수 있습니다.

1. 정상 상태에서 $$Z_1$$은 유한한 크기를 가져야 함.
2. 정상 상태에서 $$Z_2$$는 무한대로 발산해야 함.
3. $$R_x$$를 적당히 조절해서 출력 전압을 제어해야 함.

### 전압 피드백 보상기

앞서 언급했던 사항들을 어떻게 이용해야 하는지 설명하겠습니다.
제어기를 설계하려면 주파수 영역에서 설계를 해야 합니다.
따라서 ac 관점에서 회로를 다시 볼 필요가 있습니다.
ac 관점에서는 dc 값만 가지는 $$V_{ref}$$가 $$0$$이고, 가상 단락으로 인해 $$R_x$$의 양단의 전위가 $$0$$으로 같습니다.
따라서 Op-Amp의 반전 단자에서 KCL을 적용하면 다음과 같습니다.

$$
\frac{-v_{ctrl}}{Z_2}+\frac{-v_o}{Z_1}=0
$$

식을 정리하면 다음과 같습니다.

$$
\begin{align*}
		&\frac{v_{ctrl}}{v_o}=-\frac{Z_2}{Z_1}=-F_v\\
		&F_v=\frac{Z_2}{Z_1}
	\end{align*}
$$

$$F_v$$가 바로 **전압 피드백 보상기(Voltage Feedback Compensator)**의 전달 함수를 나타냅니다.
이 피드백 보상기는 $$R_x$$에 의존하지 않습니다.
이 피드백 보상기를 설계할 때는 앞서 언급한 사항들을 고려해야 합니다.

1. 정상 상태에서 $$Z_1$$은 유한한 크기를 가져야 함.
2. 정상 상태에서 $$Z_2$$는 무한대로 발산해야 함.


### PWM 블록의 소신호 모델

다음으로 PWM 블록을 소신호 모델링해봅시다.
PWM은 기본적으로 다음과 같이 제어 전압$$(v_{ctrl})$$과 기준 신호$$(v_{ramp})$$를 비교하는 방식으로 듀티 비를 결정합니다.

$$
q(t)=\begin{cases}
			1\ \ \ \text{for }v_{ctrl}>v_{ramp}\\
			0\ \ \ \text{for }v_{ctrl}<v_{ramp}
		\end{cases}
$$



## 같이 보기

- [컨버터 모델링]()
- [컨버터의 평균화 모델]()
- [컨버터의 전달 함수]()

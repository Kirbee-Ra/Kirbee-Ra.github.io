컨버터의 소신호 모델
=

---

## 목차
- [소신호 모델링](#소신호-모델링)
- [선형화](#선형화)
- [PWM 스위치의 소신호 모델](#pwm-스위치의-소신호-모델)
- [비절연형 파워 스테이지의 소신호 모델](#비절연형-파워-스테이지의-소신호-모델)
- [컨버터의 전압 모드 제어](#컨버터의-전압-모드-제어)
- [컨버터의 소신호 모델](#converter-ss-model)
- [입력단 필터를 고려한 소신호 모델]
- [DCM에서의 소신호 모델]
- [절연형 파워 스테이지의 소신호 모델]
- 

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
선형화를 하는 두 가지 방법이 있습니다.
첫째로 테일러 급수를 이용한 근사입니다.
두번째로 대입을 통한 근사입니다.

### 테일러 급수

먼저 테일러 급수를 이용한 근사에 대해 설명하겠습니다.
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

여기서 소신호의 크기는 $$1$$에 비해 매우 작다고 가정합니다.
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

여기서 $$Y,f(X)$$는 dc항이고, $$2$$차 이상의 항은 매우 작아서 무시할 수 있습니다.
따라서 **소신호 모델(Small-Signal Model)**에 대한 식은 다음과 같습니다.

$$
\begin{align*}
		&\hat{y}=\frac{df}{dx}\Big\vert_{x=X}\hat{x}\\
		&\frac{\hat{y}}{\hat{x}}=\frac{df}{dx}\Big\vert_{x=X}
		\end{align*}
$$

혹은 **소신호 이득(Small-Signal Gain)**이라고 합니다.

### 대입을 통한 근사

테일러 급수를 이용하지 않고 직접 대입을 하여 소신호 모델 표현식을 얻을 수도 있습니다. 다음과 같이 동작점 $$\left(X,f(X)\right)$$에서 소신호 $$\hat{x}$$를 가했다고 해봅시다.

$$
x=X+\hat{x}
$$

출력 신호는 다음과 같이 나타낼 수 있습니다.

$$
Y+\hat{y}=f(X+\hat{x})
$$

우변을 다음과 같이 표현할 수 있습니다.

$$
f(X+\hat{x})=D(X)+S(X)\hat{x}+O(\hat{x}^2)
$$

$$D(X)$$는 동작점에만 의존하는 dc항, $$S(X)\hat{x}$$은 소신호에 대한 1차항, $$O(\hat{x}^2)$$은 소신호에 대한 고차항입니다.
우리가 관심을 갖는 것은 입력 소신호와 출력 소신호의 선형 관계식이므로 다음과 같이 나타낼 수 있습니다.

$$
Y+\hat{y}=D(X)+S(X)\hat{x}+O(\hat{x}^2)
$$

dc항과 고차항을 제외하고 소신호에 대한 식만 보면 다음과 같습니다.

$$
\hat{y}=S(X)\hat{x}
$$

소신호 이득은 다음과 같습니다.

$$
\frac{\hat{y}}{\hat{x}}=S(X)
$$

---

## 평균화 모델의 선형화

선형화는 상태 공간 평균화 모델이나 회로 평균화 모델에 적용할 수 있습니다.
상태 공간 평균화 모델의 경우, 각 표현식들을 동작점에 대해 전부 선형화 작업을 해야 합니다.
회로 평균화 모델의 경우, 모든 소자의 동작이 평균화된 상태이고, PWM 스위치만 선형화하면 됩니다.
따라서 후자의 경우가 더 간단하므로 회로 평균화 모델을 이용하여 설명하겠습니다.

### PWM 스위치의 소신호 모델

수동 소자의 동작은 비례 관계나 1차 미분 연산으로만 표현되므로 선형적입니다.
하지만 PWM 과정은 비선형적입니다.
따라서 PWM 스위치만 선형화하면 됩니다.
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

대입을 통해 
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

이 관계식을 살펴보면 각 식에 동작점이 포함되어 있습니다.
따라서 이 관계식은 동작점에 따라 달라지는 것을 알 수 있습니다.

관계식을 다시 살펴봅시다.
소신호 전압과 소신호 전류는 정상 상태 듀티 비 $$D$$가 곱해져 있으므로 턴 비가 $$1:D$$인 이상 변압기로 모델링할 수 있습니다.
소신호 듀티의 경우는 정상 상태 전압과 정상상태 전류와의 곱으로 나타납니다.
이는 종속 전압원과 종속 전류원으로 모델링할 수 있습니다.
PWM 스위치의 소신호 모델은 다음과 같습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/소신호 스위치.png" alt="PWM 스위치의 소신호 모델" width="80%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. PWM 스위치의 소신호 모델)
  </figcaption>
</figure>

이렇게 PWM 스위치의 소신호 모델링을 마쳤습니다.

---

## 파워 스테이지의 소신호 모델

이제 파워 스테이지의 소신호 모델을 구해봅시다.
먼저 PWM 스위치를 소신호 모델링된 스위치로 변경합니다.

우리가 관심을 갖는 소신호는 입력 전압 소신호, 듀티 비 소신호, 부하 전류 소신호입니다.
이들에 해당하는 외란이 발생했을 때, 출력 전압이 어떻게 변하는지 분석을 해야 합니다.
앞서 수행한 소신호 모델링을 통해 듀티 비 소신호에 대한 정보는 이미 담겼습니다.
입력 전압 소신호와 출력 전압 소신호는 회로 법칙을 통해 관계식을 찾을 수 있습니다.
마지막으로 부하 전류 변동을 의미하는 부하 전류 소신호를 모델링해야 합니다.
이는 다음과 같이 부하 양단에 독립 전류원으로 구성할 수 있습니다.

이 과정을 거쳐 도출된 파워 스테이지의 소신호 모델입니다.

### [벅 컨버터]

벅 파워 스테이지의 소신호 모델은 다음과 같습니다.

### [부스트 컨버터]

부스트 파워 스테이지의 소신호 모델은 다음과 같습니다.

### [벅-부스트 컨버터]

벅-부스트 파워 스테이지의 소신호 모델은 다음과 같습니다.

---

## 파워 스테이지의 주파수 응답

컨버터를 설계할 때 관심을 갖는 소신호는 다음의 세 가지입니다.

- 입력 전압 변동
- 듀티 비 변동
- 부하 전류 변동

이 변수들의 변동에 의해 출력 전압이 어떻게 변하는지 분석을 해야 합니다.
이런 분석은 주파수 영역에서 수행하는 것이 유리합니다.
주파수 영역에서 분석을 해야 다양한 주파수를 가진 소신호에 대해 컨버터의 동작이 어떻게 변하는지 확인할 수 있습니다.

### 주파수 영역 변환

먼저 소신호 모델을 주파수 영역으로 변환해야 합니다.
과정은 간단합니다.
시간 변수는 모두 주파수 변수 $$s$$로 바꾸고, 인덕터와 축전기의 임피던스를 주파수 영역의 변수로 표현하면 됩니다.

### [전달 함수](./ConverterTransferFunction.md)

다음으로 컨버터의 전달 함수를 구해야 합니다.
전달 함수는 입력 변수 대비 출력 변수의 비 입니다.
하나의 입력에 대해 하나의 출력만 분석하는 것이므로, 다른 변수의 변화는 모두 $$0$$이라고 가정합니다.

다음의 세 전달 함수가 핵심 요소입니다.

1. 개루프 입력-출력 전달 함수 $$G_{vs}(s)=\displaystyle\frac{\hat{v}_o(s)}{\hat{v}_{in}(s)}$$
2. 개루프 듀티 비-출력 전달 함수 $$G_{vd}(s)=\displaystyle\frac{\hat{v}_o(s)}{\hat{d}(s)}$$
3. 개루프 출력 임피던스 전달 함수 $$Z_p(s)=\displaystyle\frac{\hat{v}_o(s)}{\hat{i}_o(s)}$$

이 전달 함수들은 회로 법칙을 통해 구할 수 있습니다.
구한 전달 함수들의 보드 선도를 그리고, 이득과 위상에 대한 정보를 확인하면 됩니다.

---

## [컨버터의 전압 모드 제어](./ConverterVMC.md)

지금까지 봐온 소신호 모델은 파워 스테이지에 대한 내용이었습니다.
이제 피드백 회로가 있는 전체 컨버터에 대해 설명하겠습니다.
다음은 가장 기본적인 **[전압 모드 제어(Voltage Mode Control)](./ConverterVMC.md)**를 이용한 컨버터입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/VMC 기본.png" alt="VMC 기본" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 컨버터의 전압 모드 제어 회로)
  </figcaption>
</figure>

회로를 보면 알 수 있듯이 출력 전압에 대한 정보를 받아서 다시 파워 스테이지에 수정된 값을 전송하는 구조입니다.
전압에 대한 정보만을 이용하기 때문에 전압 모드 제어라고 합니다.
제어 회로는 다음과 같이 전압 피드백 회로와 PWM 블록으로 구성됩니다.
각 부분에 대해 설명하겠습니다.

### 출력 전압 제어

먼저 전압 피드백 회로를 살펴봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/VMC 파트.png" alt="VMC 파트" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 컨버터의 전압 피드백 회로 및 PWM 블록)
  </figcaption>
</figure>

연산 증폭기의 두 단자는 가상 단락되어 있으므로 반전 단자에서 KCL을 적용하면 다음과 같습니다.

$$
\frac{V_{ref}-v_{ctrl}}{Z_2}+\frac{V_{ref}-v_o}{Z_1}+\frac{V_{ref}}{R_x}=0
$$

이 식은 다음과 같이 정리할 수 있습니다.

$$
V_{ref}-v_{ctrl}=\frac{Z_2}{Z_1}\left(v_o-V_{ref}\left(1+\frac{Z_1}{R_x}\right)\right)
$$

전압 제어가 완료되면 정상 상태로 진입합니다.
정상 상태에서는 시간에 의존하는 항이 $$0$$이 되고, dc 항만 남으므로 $$s=j0$$을 통해 계산합니다.
정상 상태에서 다음을 가정해봅시다.

$$
\left\vert\frac{Z_2(j0)}{Z_1(j0)}\right\vert\rightarrow\infty
$$

컨버터가 정상 동작 하려면 $$v_{ctrl}$$의 범위는 연산 증폭기 출력 전압의 상한과 하한 사이가 되어야 합니다.
$$V_{ref}-v_{ctrl}$$은 발산하지 않으므로 등식이 성립하려면 다음 조건이 필요합니다.

$$
V_o-V_{ref}\left(1+\frac{\left\vert Z_1(j0)\right\vert}{R_x}\right)=0
$$

따라서 정상 상태에서 출력 전압은 다음과 같습니다.

$$
V_o=V_{ref}\left(1+\frac{\left\vert Z_1(j0)\right\vert}{R_x}\right)
$$

이 식이 바로 출력 전압 레귤레이션을 의미합니다.
출력 전압이 $$Z_1,R_x$$에 의존하는 것을 알 수 있습니다.
앞선 가정을 통해 출력 전압을 제어하는 방법을 알 수 있습니다.
제어기를 설계할 때 다음 세 가지를 기억해야 합니다.

1. 정상 상태에서 $$Z_1$$은 유한한 크기를 가져야 합니다.
2. 정상 상태에서 $$Z_2$$는 무한대로 발산해야 합니다.
3. $$R_x$$를 적당히 조절해서 출력 전압을 제어해야 합니다.

### 전압 피드백 보상기

앞서 언급했던 사항들을 어떻게 이용해야 하는지 설명하겠습니다.
제어기를 설계하려면 주파수 영역에서 설계를 해야 합니다.
따라서 ac 관점에서 회로를 다시 볼 필요가 있습니다.
ac 관점에서는 dc 값만 가지는 $$V_{ref}$$가 $$0$$이고, 가상 단락으로 인해 $$R_x$$의 양단의 전위가 $$0$$으로 같습니다.
따라서 연산 증폭기의 반전 단자에서 KCL을 적용하면 다음과 같습니다.

$$
\frac{-v_{ctrl}}{Z_2}+\frac{-v_o}{Z_1}=0
$$

식을 정리하면 다음과 같습니다.

$$
\begin{align*}
		&\frac{v_{ctrl}}{v_o}=-\frac{Z_2}{Z_1}=-F_v\\
		&\rightarrow F_v=\frac{Z_2}{Z_1}
	\end{align*}
$$

$$F_v$$가 바로 **전압 피드백 보상기(Voltage Feedback Compensator)**의 전달 함수를 나타냅니다.
이 피드백 보상기는 $$R_x$$에 의존하지 않습니다.
이 피드백 보상기를 설계할 때는 앞서 언급한 사항들을 고려해야 합니다.

1. 정상 상태에서 $$Z_1$$은 유한한 크기를 가져야 합니다.
2. 정상 상태에서 $$Z_2$$는 무한대로 발산해야 합니다.


### PWM 블록의 소신호 모델

다음으로 PWM 블록을 소신호 모델링해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/VMC 파트.png" alt="VMC 파트" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 컨버터의 전압 피드백 회로 및 PWM 블록)
  </figcaption>
</figure>

PWM은 기본적으로 다음과 같이 제어 전압$$(v_{ctrl})$$과 기준 신호$$(v_{ramp})$$를 비교하는 방식으로 듀티 비를 결정합니다.

$$
q(t)=\begin{cases}
			1\ \ \ \text{for }v_{ctrl}>v_{ramp}\\
			0\ \ \ \text{for }v_{ctrl}<v_{ramp}
\end{cases}
$$

듀티 비는 다음과 같이 결정됩니다.

$$
\begin{align*}
		&d_kT_s:T_s=v_{ctrl}(t_k):V_m\\
		&\rightarrow d_k=\frac{v_{ctrl}(t_k)}{V_m}
	\end{align*}
$$

제어 전압이 스위칭 주기에 비해 매우 천천히 변화한다고 가정하면 다음과 같이 근사할 수 있습니다.

$$
d(t)\approx\frac{v_{ctrl}}{V_m}
$$

평균화를 하면 다음과 같습니다.

$$
\overline{d}(t)=\frac{\overline{v}_{ctrl}}{V_m}
$$

선형화를 하면 다음과 같습니다.

$$
D+\hat{d}=\frac{V_{ctrl}+\hat{v}_{ctrl}}{V_m}
$$

소신호 표현식은 다음과 같습니다.

$$
\hat{d}=\frac{\hat{v}_{ctrl}}{V_m}
$$

전압 피드백 보상기는 $$v_{ctrl}$$를 출력합니다.
PWM 블록은 듀티 정보를 출력하므로 다음의 전달 함수를 구해야 합니다.

$$
F_m=\frac{\hat{d}}{\hat{v}_{ctrl}}
$$

이는 소신호 표현식을 통해 다음과 같이 구할 수 있습니다.

$$
F_m=\frac{1}{V_m}
$$

이 전달 함수를 **PWM 이득(PWM Gain)**이라고 합니다.

---
<h2 id="converter-ss-model">컨버터의 소신호 모델</h2>

파워 스테이지, 전압 피드백 보상기, PWM 블록까지 모두 소신호 모델링을 마쳤습니다.
전체 시스템을 다음과 같이 나타낼 수 있습니다.

(SMPS)

블록 다이어그램으로 나타내면 다음과 같습니다.

(BD)

전압 피드백 경로를 살펴보면 전압 피드백 회로의 전달 함수에 $$-$$부호가 붙는 것을 알 수 있습니다.
이는 전압 피드백이 **음성 피드백(Negative Feedback)**을 통해 수행되는 것을 의미합니다.

어떤 입력 변수 $$\hat{x}$$와 출력 전압 사이의 개루프 전달 함수를 $$G(s)$$라고 해봅시다.
이 변수 $$\hat{x}$$에 대한 컨버터의 폐루프 전달 함수는 다음과 같이 나타낼 수 있습니다.

$$
	\begin{align*}
&G(s)=\frac{\hat{v}_o}{\hat{x}}\Big\vert_{OL}\\
&\hat{v}_o=G(s)\hat{x}+\left(-F_v(s)\right)F_mG_{vd}(s)\\
&\rightarrow \frac{\hat{v}_o}{\hat{x}}\Big\vert_{CL}=\frac{G(s)}{1+F_v(s)F_mG_{vd}(s)}
	\end{align*}
$$

개루프 전달 함수는 $$G_{vs}(s)$$일 수도 있고, $$Z_p(s)$$일 수도 있습니다.

---

## 입력단 필터를 고려한 소신호 모델

실제 컨버터에서는 전원과 파워 스테이지 사이에 필터를 이용합니다.
이는 노이즈 및 리플을 감쇠하기 위해 활용됩니다.

---

## DCM에서의 소신호 모델

지금까지 살펴본 소신호 모델은 모두 CCM에서의 동작을 모델링한 것입니다.
이제 DCM에서 대해 생각해봅시다.
인덕터 전류 파형은 다음과 같이 나타납니다.

<figure style="text-align: center;">
  <img src="./PEFigure/DCM 인덕터 전류.png" alt="DCM 인덕터 전류" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. DCM에서의 인덕터 전류)
  </figcaption>
</figure>

보시는 바와 같이 전류가 흐르지 않는 구간이 존재합니다.
PWM 스위치를 다시 살펴봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/DCM PWM 스위치.png" alt="DCM PWM 스위치" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. PWM 스위치)
  </figcaption>
</figure>

CCM과 달리 살펴볼 변수는 $$v_{ac},v_{cp},i_a,i_p$$입니다.
$$i_a$$의 평균은 다음과 같습니다.

$$
	\begin{align*}
\overline{i}_a&=\frac{1}{T_s}\int_{T_s}i_adt=\frac{dT_s}{T_s}\frac{1}{dT_s}\int_{0}^{dT_s}i_adt\\
&=\frac{i_{L,pk}}{2}d
\end{align*}
$$

또한 $$i_p$$의 평균은 다음과 같습니다.

$$
	\begin{align*}
\overline{i}_p&=\frac{1}{T_s}\int_{T_s}i_pdt=\frac{d_1T_s}{T_s}\frac{1}{d_1T_s}\int_{dT_s}^{dT_s+d_1T_s}i_pdt\\
&=\frac{i_{L,pk}}{2}d
\end{align*}
$$

이제 인덕터 전류의 피크 값을 구해봅시다.


---

## 절연형 파워 스테이지의 소신호 모델

절연형 파워 스테이지는 변압기를 활용하여 1차측과 2차측을 전기적으로 절연하는 형태를 띱니다.
변압기를 활용함으로써 감전 시에는 더 적은 에너지(2차측)만 우리 몸으로 흘러들어옵니다.
비절연형 컨버터의 경우는 전원의 에너지가 그대로 흘러들어오기 때문에 절연형 컨버터가 비교적 안전합니다.
또한 턴 비를 조절하여 동일한 듀티 비로도 출력 전압을 더 세밀하게 조절할 수 있습니다.
비절연형 컨버터에서 듀티 비가 너무 낮으면 PWM IC가 우리가 원하는 동작을 하지 않을 수 있습니다.

### 포워드 컨버터

먼저 포워드 컨버터를 살펴봅시다.
포워드 컨버터는 벅 컨버터 기반의 절연형 컨버터로, 주로 권선 리셋형이 이용됩니다.


---

## 같이 보기

- [컨버터 모델링](./ConverterModeling.md)
- [컨버터의 평균화 모델](./AveragedModel.md)
- [파워 스테이지의 전달 함수](./ConverterTransferFunction.md)

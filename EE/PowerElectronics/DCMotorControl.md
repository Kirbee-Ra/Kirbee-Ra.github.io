직류 전동기의 제어
=

---

## 목차
- [과도 상태 해석](#과도-상태-해석)
- [제어 시스템](#제어-시스템)
- [제어기 설계 고려 사항](#제어기-설계-고려-사항)
- [전류 제어기](#전류-제어기)
- [속도 제어기](#속도-제어기)
- [위치 제어기](#위치-제어기)

---

## 과도 상태 해석

외부 요인이 시스템에 영향을 줄 경우, 과도 상태를 거쳐 다시 정상 상태에 도달하도록 제어기가 동작합니다.
제어기를 설계하기 위해서는 시스템의 과도 상태를 해석할 필요가 있습니다.

### 응답 특성

---

## 제어 시스템

원하는 출력을 얻고자 할 때, 제어를 통해 입력을 변화시킵니다.
전동기 제어 시스템에서는 제어 변수로 전류, 토크, 자속, 속도, 위치 등을 이용합니다.
(이하 각위치는 위치, 각속도는 속도로 표기합니다.)

제어기의 성능은 두 지표를 통해 평가합니다.
1. 지령 추적: 출력을 지령 값과 동일하도록 변화시킵니다.
2. 외란 방어: 외란으로부터의 영향을 받지 않도록 합니다.

### 전동기 구동 시스템

전동기 구동 시스템은 토크를 발생시켜 전동기를 운동시킵니다.
따라서 다음 과정을 통해 제어를 합니다.
1. 전동기나 부하의 각위치를 제어하기 위해 속도를 제어.
2. 속도를 제어하기 위해 토크를 제어.

정상 상태에서는 전기자 전압이나 계자 자속을 통해 속도를 제어할 수 있습니다.
과도 상태에서 위치와 속도를 제어하기 위해서는 전동기 토크가 스스로 제어되어야 합니다.
토크 센서를 이용하여 제어할 수 있지만 비싼 가격으로 인해 경제적이지 않습니다.
일반적으로 전기자 전류를 통해 토크를 제어할 수 있습니다.
계자 자속이 일정할 때, 전동기 토크는 전기자 전류에 비례합니다.

$$
\tau_e=k_T\Phi_f i_a
$$

그리고 전기자 전압과 전기자 전류의 관계는 다음과 같습니다.

$$
v_a=R_ai_a+L_a\dot{i}_a+k_e\Phi_f\omega_m
$$

전기자 전류를 제어하기 위해서는 속도에 해당하는 전기자 전압이 가해져야 하는 것을 알 수 있습니다.

다음 그림은 전동기 구동 시스템의 블록 다이어그램입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/전동기시스템.svg" alt="전동기시스템" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 전동기 구동 시스템)
  </figcaption>
</figure>

전류 제어기, 속도 제어기, 위치 제어기가 캐스케이딩된 구조입니다.
내부 제어 루프가 외부 제어 루프에 비해 응답이 매우 빨라야 각 제어 루프를 독립적으로 설계할 수 있습니다.

### 개루프 제어

다음 그림은 **개루프 시스템(Open-Loop System)**으로 기본적인 제어 시스템입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/개루프.svg" alt="개루프" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 개루프 시스템)
  </figcaption>
</figure>

지령 값을 제어기에 입력하고, 제어기의 출력이 시스템에 입력되어 최종적으로 지령 값과 같은 출력을 얻는 시스템입니다.
하지만 시스템 파라미터에 오차가 존재하거나, 약간의 외란만 가해져도 출력이 지령 값과 다르게 나타납니다.
따라서 정확한 제어를 하기 어렵습니다.

### 폐루프 제어(피드백 제어)

앞서 소개한 개루프 제어의 문제를 해결하기 위해 설계된 시스템이 있습니다.
바로 **폐루프 시스템(Closed-Loop System)**입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/폐루프.svg" alt="폐루프" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 폐루프 시스템)
  </figcaption>
</figure>

폐루프 시스템은 출력과 지령 값의 차이(오차)를 제어기에 입력하여 시스템의 입력을 변화시키고, 최종적으로 출력을 제어합니다.
출력 정보를 이용하기 위해서는 센서가 필요합니다.
이 폐루프 시스템은 전동기 구동 시스템에서 가장 널리 이용되는 시스템입니다.
목표는 오차를 $$0$$으로 만드는 것이고, 이 과정에서 여러 제어 기법이 이용됩니다.

### 비례 제어(P 제어)

먼저 **비례 제어(Proportional(P) Control)**입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/비례제어.svg" alt="비례제어" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 비례 제어 시스템)
  </figcaption>
</figure>

말 그대로 오차에 비례 상수 $$K_p$$를 곱하여 시스템에 다시 입력하는 방식입니다.

$$
u(t)=K_pe(t)
$$

현재 제어 사이클의 오차를 증폭하여 다시 시스템에 입력하므로 응답 속도가 빠릅니다.

비례 제어 시스템의 오차는 다음과 같이 구할 수 있습니다.

$$
\begin{align*}
	&E(s)=R(s)-E(s)K_pG_p(s)\\
	&\rightarrow E(s)=\frac{R(s)}{1+K_pG_p(s)}
\end{align*}
$$

지령 값은 보통 상수(계단 함수)로, $$s$$ 영역에서는 다음과 같이 나타납니다.

$$
R(s)=\frac{R_0}{s}
$$

따라서 오차는 다음과 같습니다.

$$
E(s)=\frac{1}{1+K_pG_p(s)}\frac{R_0}{s}
$$

정상 상태 오차는 최종값 정리를 이용하면 다음과 같습니다.

$$
\begin{align*}
	\lim_{t\rightarrow\infty}e(t)&=\lim_{s\rightarrow0}sE(s)\\
	&=\lim_{s\rightarrow0}\frac{R_0}{1+K_pG_p(s)}\\
	&=\frac{R_0}{1+K_p\displaystyle\lim_{s\rightarrow0}G_p(s)}
\end{align*}
$$

일반적인 전동기 시스템에서 위 값은 양수입니다.
즉, 오차가 $$0$$이 되지 않는다는 의미입니다.
제어 사이클을 거듭할수록 제어량이 점점 줄어들어 더 이상 제어를 할 수 없는 상태가 됩니다.
따라서 비례 제어만으로는 오차를 $$0$$으로 만들 수 없습니다.

### 적분 제어(I 제어)

다음으로 **적분 제어(Integral(I) Control)**입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/적분제어.svg" alt="적분제어" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 적분 제어 시스템)
  </figcaption>
</figure>

초기부터 현재까지 누적된 오차를 통해 제어하는 기법입니다.

$$
u(t)=K_i\int_{t_0}^te(t')dt'
$$

제어 사이클마다 초기 오차부터 현재 오차까지 누적하기 때문에 응답 속도가 느립니다.

적분 제어 시스템의 오차는 다음과 같이 구할 수 있습니다.

$$
\begin{align*}
&E(s)=R(s)-E(s)\frac{K_i}{s}G_p(s)\\
	&\rightarrow E(s)=\frac{sR(s)}{s+K_pG_p(s)}
\end{align*}
$$

계단 함수 지령 값을 이용하면 오차는 다음과 같습니다.

$$
\begin{align*}
&E(s)=R(s)-E(s)\frac{K_i}{s}G_p(s)\\
	&\rightarrow E(s)=\frac{R_0}{s+K_pG_p(s)}
\end{align*}
$$

최종값 정리를 통해 정상 상태 오차를 구하면 다음과 같습니다.

$$
\begin{align*}
	\lim_{t\rightarrow\infty}e(t)&=\lim_{s\rightarrow0}sE(s)\\
	&=\lim_{s\rightarrow0}\frac{sR_0}{s+K_pG_p(s)}\\
	&=0
\end{align*}
$$

적분 제어를 통해 정상 상태 오차를 제거할 수 있음을 알 수 있습니다.
제어 사이클을 거듭하며 오차 함수가 $$0$$이 되면 더 이상 오차가 누적되지 않고, 오차가 $$0$$이 된 시점의 제어기 출력이 시스템에 계속 입력됩니다.

### 비례적분 제어(PI 제어)

비례 제어는 정상 상태 오차를 $$0$$으로 만들 수 없고, 적분 제어는 느리다는 단점이 있습니다.
정상 상태 오차를 $$0$$으로 만들면서, 응답 속도도 개선이 된 제어 기법이 바로 **비례적분 제어(Proportional-Integral(PI) Control)**입니다. 

### 피드포워드 제어

---

## 제어기 설계 고려 사항

### 안정도

### 응답 속도

### 정상 상태 오차

---

## 전류 제어기

---

## 속도 제어기

---

## 위치 제어기

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

말 그대로 오차에 비례 이득 $$K_p$$를 곱하여 시스템에 다시 입력하는 방식입니다.

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

초기부터 현재까지 누적된 오차에 적분 이득 $$K_i$$를 곱한 값을 통해 제어하는 기법입니다.

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
E(s)=\frac{R_0}{s+K_pG_p(s)}
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

<figure style="text-align: center;">
  <img src="./PEFigure/비례적분제어.svg" alt="비례적분제어" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 비례적분 제어 시스템)
  </figcaption>
</figure>

비례 항과 적분 항을 합하여 시스템에 입력하는 방식입니다.

$$
u(t)=K_pe(t)+K_i\int_{t_0}^te(t')dt'
$$

비례적분 제어의 오차는 다음과 같습니다.

$$
\begin{align*}
&E(s)=R(s)-E(s)\left(K_p+\frac{K_i}{s}\right)G_p(s)\\
&\rightarrow E(s)=\frac{sR(s)}{s\left(1+K_pG_p(s)\right)+K_iG_p(s)}
\end{align*}
$$

계단 함수 지령 값을 이용하면 다음과 같습니다.

$$
E(s)=\frac{R_0}{s\left(1+K_pG_p(s)\right)+K_iG_p(s)}
$$

최종값 정리를 이용하면 정상 상태 오차는 다음과 같습니다.

$$
\begin{align*}
\lim_{t\rightarrow\infty}e(t)&=\lim_{s\rightarrow0}sE(s)\\
&=\lim_{s\rightarrow0}\frac{sR_0}{s\left(1+K_pG_p(s)\right)+K_iG_p(s)}\\
&=0
\end{align*}
$$


### 피드포워드 제어

외란에 대해 피드백 제어보다 빠르게 제어하는 법이 있습니다.
바로 **피드포워드 제어(Feedforward Control)**입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/피드포워드제어.svg" alt="피드포워드제어" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 피드포워드 및 피드백 제어 시스템)
  </figcaption>
</figure>

피드포워드 제어를 이용하지 않는 경우를 생각해봅시다.
외란에 의해 시스템 입력이 변하고, 출력에 반영됩니다.
그리고 오차를 보상하기 위해 제어기가 작동하고, 제어기 출력이 다시 시스템에 입력되어 출력에 반영됩니다.
많은 과정을 거치기 때문에 응답이 느립니다.
피드포워드 제어를 이용하면, 시스템 입력에 바로 외란을 보상하는 신호가 더해지므로, 이전보다 빠르게 제어할 수 있습니다.
일반적으로 피드백 제어를 보조하는 역할로 사용됩니다.
만약 외란이나 시스템에 대한 정보가 부정확하다면, 피드포워드 제어에 문제가 생길 수 있습니다.

---

## 제어기 설계 고려 사항

비례적분 제어의 경우, 비례 이득 및 적분 이득이 제어기의 성능을 결정합니다.
이 이득들은 다음의 요소들을 고려하여 설계되어야 합니다.
1. 안정도
2. 응답 속도
3. 정상 상태 오차

이 중에서 안정도가 가장 중요합니다.
시스템이 우선 안정적으로 동작해야 그 이후의 설계가 유의미합니다.

### 안정도

### 응답 속도

### 정상 상태 오차

---

## 전류 제어기

전동기 토크는 전기자 전류에 비례합니다.

$$
\tau_e=k_T\Phi_fi_a
$$

부하의 속도와 위치를 제어하기 위해 토크가 먼저 제어되어야 합니다.
이는 전기자 전류를 통해 제어하므로 전류 제어기가 전체 시스템에서 가장 안쪽 루프에 위치합니다.

<figure style="text-align: center;">
  <img src="./PEFigure/전기자전류제어기.svg" alt="전기자전류제어기" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 전류 제어기)
  </figcaption>
</figure>

비례적분 제어기의 전달 함수가 다음과 같다고 해봅시다.

$$
G_{PI}(s)=K_{pc}+\frac{K_{ic}}{s}
$$

전기자 전류는 다음과 같습니다.

$$
\begin{align*}
&I_a(s)=\left(\left(I_a^*(s)-I_a(s)\right)\left(K_{pc}+\frac{K_{ic}}{s}\right)-E_a(s)\right)\frac{1}{R_a+sL_a}\\
&\rightarrow I_a(s)=\frac{sK_{pc}+K_{ic}}{s^2L_a+s\left(R_a+K_{pc}\right)+K_{ic}}I_a^*(s)-\frac{s}{s^2L_a+s\left(R_a+K_{pc}\right)+K_{ic}}E_a(s)
\end{align*}
$$

전동기 제어 시스템에서 역기전력은 전기자 전압 및 전류에 영향을 미치는 외란으로 취급됩니다.
역기전력은 속도에 비례하므로 속도를 측정하여 피드포워드 제어를 통해 보상합니다.

<figure style="text-align: center;">
  <img src="./PEFigure/역기전력외란.svg" alt="역기전력외란" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 역기전력이 보상된 전류 제어기)
  </figcaption>
</figure>

이때 이 시스템의 전달 함수는 다음과 같습니다.

$$
\frac{I_a(s)}{I_a^*(s)}=\frac{sK_{pc}+K_{ic}}{s^2L_a+s\left(R_a+K_{pc}\right)+K_{ic}}
$$

### 비례적분 제어기 설계

이제 이 시스템은 비례적분 제어기의 이득에 따라 성능이 결정됩니다.
시스템의 루프 이득은 다음과 같습니다.

$$
\begin{align*}
G_L(s)&=\left(K_{pc}+\frac{K_{ic}}{s}\right)\frac{1}{sL_a+R_a}\\
&=\frac{K_{pc}}{sL_a}\frac{s+K_{ic}/K_{pc}}{s+R_a/L_a}
\end{align*}
$$

루프 이득의 극점은 전동기의 파라미터 $$R_a,L_a$$로 결정되고, 영점은 비례적분 제어기의 이득으로 결정됩니다.
비례적분 제어기의 이득을 다음과 같이 설정해봅시다.

$$
\frac{K_{ic}}{K_{pc}}=\frac{R_a}{L_a}
$$

이렇게 설정하면 극점-영점 상쇄가 일어나서 전달 함수가 다음과 같이 간단해집니다.

$$
G_L(s)=\frac{K_{pc}}{sL_a}
$$

이때 폐루프 전달 함수는 다음과 같습니다.

$$
\begin{align*}
\frac{I_a(s)}{I_a^*(s)}&=\frac{\displaystyle\frac{K_{pc}}{sL_a}}{1+\displaystyle\frac{K_{pc}}{sL_a}}\\
&=\frac{\displaystyle\frac{K_{pc}}{L_a}}{s+\displaystyle\frac{K_{pc}}{L_a}}
\end{align*}
$$

이는 1차 저역 필터의 전달 함수로, 차단 주파수 $$\omega_{cc}=\displaystyle\frac{K_{pc}}{L_a}=\displaystyle\frac{K_{ic}}{R_a}$$를 이용하여 다음과 같이 나타낼 수 있습니다.

$$
\frac{I_a(s)}{I_a^*(s)}=\frac{\omega_{cc}}{s+\omega_{cc}}
$$

비례적분 제어기의 이득을 조정하여 차단 주파수를 조정할 수 있습니다.
이를 통해 입력 신호(지령 값)가 출력단에 그대로 전달되고, 고주파 노이즈는 감쇄되게 할 수 있습니다.

### 적분기의 와인드업

이상적인 시스템은 입력 전압(전기자 전압)을 임의로 설정할 수 있습니다.
하지만 실제로는 다음과 같은 스위칭 회로가 이용됩니다.

<figure style="text-align: center;">
  <img src="./PEFigure/하프브릿지스위칭.svg" alt="하프브릿지스위칭" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 하프 브릿지 스위칭 회로)
  </figcaption>
</figure>

따라서 입력 전압의 범위가 제한됩니다.
이는 블록 다이어그램에서 다음과 같이 제한기를 이용하여 표현할 수 있습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/전류제어제한기.svg" alt="전류제어제한기" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 전기자 전압의 제한을 고려한 전류 제어기)
  </figcaption>
</figure>

비례적분 제어기를 지나 피드포워드 제어(역기전력 보상)가 된 전기자 전압이 제한기를 거쳐서 입력되는 구조입니다.
이 제한기로 인해서 시스템에 입력되어야 하는 전기자 전압보다 더 낮은 값이 입력됩니다.
즉, 현재 제어 사이클에서 발생한 오차를 모두 보상하지는 못합니다.
일부만 보상하는 제어를 반복하면서 응답 속도가 느려집니다.
일부만 보상하기 때문에 이상적인 경우보다 제어 사이클마다 발생하는 오차가 비교적 큽니다.
이 과정에서 오차가 과하게 누적되면서 지령 값보다 더 큰 값을 출력하게 됩니다.
이를 **와인드업(Windup)** 현상이라고 합니다.
와인드업이 발생하면 다시 지령 값으로 돌아가는데 시간이 오래 걸립니다.
때로는 발산하기도 합니다.

### 안티 와인드업: 역 계산

와인드업 현상을 방지하기 위해 **안티 와인드업(Anti-Windup)** 기법을 이용합니다.
그 중에서 대표적인 **역 계산(Back Calculation)**에 대해 설명하겠습니다.
문제의 원인은 오차의 과한 누적으로, 적분기를 조금 수정해야 합니다.
오차가 기존보다 적게 누적되도록 하려면 적분기의 입력을 줄일 필요가 있습니다.
이 오차는 제한기로부터 영향을 받으므로, 제한기의 입력과 출력 정보를 이용하여 다음과 같이 설계할 수 있습니다.

$$
<figure style="text-align: center;">
  <img src="./PEFigure/역계산.svg" alt="역계산" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 역 계산을 통한 안티 와인드업)
  </figcaption>
</figure>
$$

제한기의 입력과 출력의 차이를 스케일링하여 적분기의 입력에서 빼줍니다.

### 전류 제어기 설계

---

## 속도 제어기

---

## 위치 제어기

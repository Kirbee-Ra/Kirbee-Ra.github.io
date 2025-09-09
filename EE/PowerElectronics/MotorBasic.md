전동기의 기초
=

---

## 목차

---

## 전동기

**전동기(Motor)**는 전기 에너지를 역학적 에너지로 변환하는 장치입니다.
주로 전류를 흘려서 회전 운동 에너지로 변환합니다.
전동기의 원리를 공부하기 위해서는 기초적인 전자기학 및 회전 운동에 대해 공부할 필요가 있습니다.

---

## 기초 전자기 이론

전동기 공부에 필요한 기초 전자기학을 먼저 살펴봅시다.

### 자속

그림과 같이 솔레노이드에 전류를 흘린다고 생각해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/솔레노이드.png" alt="솔레노이드" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 솔레노이드)
  </figcaption>
</figure>

솔레노이드의 단면은 다음과 같이 나타낼 수 있습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/솔레노이드 단면.png" alt="솔레노이드 단면" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 솔레노이드의 단면)
  </figcaption>
</figure>

직사각형 형태의 단면 $$S$$를 생각해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/솔레노이드 단면 S.png" alt="솔레노이드 단면 S" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 단면 S를 고려한 솔레노이드의 단면)
  </figcaption>
</figure>

이 단면 $$S$$에 대해 암페어 법칙을 적용하면 다음과 같습니다.

$$
\oint_{\partial S} \mathbf{B}\cdot d\mathbf{l}=\mu\int_S \mathbf{J}\cdot d\mathbf{a}
$$

솔레노이드 외부 자기장은 $$\mathbf{0}$$이고, 내부에서 세로 경로는 자기장과의 내적이 $$0$$이므로 다음과 같습니다.

$$
\begin{align*}
	&Bl=\mu NI\\
	&\rightarrow B=\frac{\mu NI}{l}
\end{align*}
$$

이제 다음과 같은 단면 $$A$$를 고려해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/솔레노이드 단면 A.png" alt="솔레노이드 단면 A" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 단면 A를 고려한 솔레노이드)
  </figcaption>
</figure>

단면 $$A$$를 통과하는 **자속(Magnetic Flux 또는 Flux)**은 다음과 같이 나타낼 수 있습니다.

$$
\begin{align*}
	\Phi&=\int_A \mathbf{B}\cdot d\mathbf{a}\\
	&=BA\\
	&=\frac{\mu NA}{l}I
\end{align*}
$$

자속은 특정 단면을 통과하는 자기장선의 양을 의미합니다.
솔레노이드 전체를 통과하는 자기장선의 양은 **쇄교 자속(Flux Linkage)**라고 하며 다음과 같습니다.

$$
\Lambda=N\Phi
$$

$$1$$ 턴 당 통과하는 자속이 있고, 솔레노이드는 총 $$N$$ 턴 감겨있으므로 자속에 $$N$$을 곱하면 쇄교 자속이 됩니다.

### 인덕턴스

**인덕턴스(Inductance)**는 인덕터에 흐르는 단위 전류 당 생성되는 쇄교 자속의 양을 의미합니다.

$$
L=\frac{\Lambda}{I}
$$

자기장으로부터 인덕턴스를 유도해봅시다.
먼저 암페어 법칙을 다시 살펴봅시다.

$$
\oint_{\partial S} \mathbf{H}\cdot d\mathbf{l}=\int_S \mathbf{J}\cdot d\mathbf{a}
$$

선형 매질에 대해 다음이 성립합니다.

$$
\mathbf{B}=\mu\mathbf{H}
$$

따라서 다음과 같이 쓸 수 있습니다.

$$
\oint_{\partial S} \mathbf{B}\cdot d\mathbf{l}=\mu\int_S \mathbf{J}\cdot d\mathbf{a}
$$

계산 결과는 다음과 같았습니다.

$$
B=\frac{\mu NI}{l}
$$

자속은 다음과 같습니다.

$$
\begin{align*}
	\Phi&=\int_A \mathbf{B}\cdot d\mathbf{a}\\
	&=BA
\end{align*}
$$

쇄교 자속은 다음과 같습니다.

$$
\Lambda=N\Phi
$$

인덕턴스는 다음과 같습니다.

$$
\begin{align*}
	L&=\frac{\Lambda}{I}\\
	&=\frac{\mu N^2A}{l}
\end{align*}
$$

### 투자율

**투자율(Permeability)**은 매질이 외부 자기장에 대해 자화되는 정도를 나타내는 양입니다.
진공의 투자율은 다음과 같습니다.

$$
\mu_0=4\pi\times10^{-7}\ \text{H/m}
$$

매질의 투자율에 대한 진공의 투자율을 **상대 투자율(Relative Permeability)**라고 하며 다음과 같이 나타냅니다.

$$
\mu_r=\frac{\mu}{\mu_0}
$$

선형 매질은 다음과 같이 자기장과 자속 밀도가 비례합니다.

$$
\mathbf{B}=\mu\mathbf{H}
$$

투자율의 값에 따라 물성(강자성, 상자성, 반자성)이 다릅니다.
또한 전자기파 이론에서는 복소 투자율을 다룹니다.

### 자기 포화

일반적으로 인덕터에 흐르는 전류와 자속은 다음의 관계에 있습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/i_phi.png" alt="i_phi" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 인덕터 전류와 자속의 관계)
  </figcaption>
</figure>

소전류 영역에서는 자속이 선형적으로 증가합니다.
이 구간을 **선형 영역(Linear Region)**이라고 합니다.
특정 구간부터 증가율이 줄어듭니다.
이 지점을 **무릎 점(Knee Point)**이라고 합니다.
그 이후부터는 자속이 거의 일정합니다.
이 구간을 **포화 영역(Saturation Region)**이라고 합니다.
포화 영역에서는 인덕터가 더 이상 제 기능을 하지 못합니다.
인덕터 설계 시에 반드시 고려해야 합니다.

전동기의 토크는 생성된 자속에 비례합니다.
따라서 많은 양의 자속이 필요합니다.
이에 따라 동작점을 무릎 점 또는 약간 포화된 지점에 선정합니다.

### 자기 회로

자기 회로에 대해 전기 회로에 비유하여 간단하게 설명하겠습니다.

### 수반 에너지

전류와 자속이 비례한다는 가정을 많이 하지만 실제로는 선형적이지 않습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/i_phi_real.png" alt="i_phi_real" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 비선형적인 전류와 자속의 관계)
  </figcaption>
</figure>

위 그래프에서 자기 에너지는 다음과 같이 쓸 수 있습니다.

$$
W_m=\int id\Lambda
$$

그리고 또 다른 양인 **수반 에너지(Coenergy)**는 다음과 같이 정의됩니다.

$$
W_m'=\int \Lambda di
$$

수반 에너지는 물리적인 양은 아니며, 그저 시스템을 분석하기 위해 정의된 양입니다.
전류와 자속이 비례 관계라면, 자기 에너지와 수반 에너지는 같습니다.

$$
\begin{align*}
		&\Lambda=Li\\
		&W_m=\int id\Lambda=\int\frac{\Lambda}{L}d\Lambda=\frac{\Lambda^2}{2L}\\
		&W_m'=\int \Lambda di=\int Lidi=\frac{1}{2}Li^2\\
		&W_m=W_m'
\end{align*}
$$

---

## 전동기의 동작 원리

### 병진 이동자

전동기는 기본적으로 다음과 같은 형태입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/모터.png" alt="모터" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 전동기의 구조)
  </figcaption>
</figure>

**고정자(Stator)**는 전동기 내에 고정된 부분으로, 전기 에너지를 자기 에너지로 전환하는 역할을 수행합니다.
**이동자(Mover)**는 전동기 내에서 움직이는 부분으로, 자기 에너지를 역학적 에너지로 전환하는 역할을 수행합니다.

총 에너지 보존 식은 다음과 같이 쓸 수 있습니다.

$$
W_e=W_m+W_{mec}
$$

$$W_e$$는 공급된 전기 에너지, $$W_m$$은 저장된 자기 에너지, 그리고 $$W_{mec}$$는 출력된 역학적 에너지입니다.
좌표계를 다음과 같이 설정합시다.

<figure style="text-align: center;">
  <img src="./PEFigure/모터좌표.png" alt="모터좌표" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 전동기와 좌표계)
  </figcaption>
</figure>

고정자에 공급되는 전기 에너지는 다음과 같습니다.

$$
W_e=\int \mathcal{E}i dt
$$

패러데이 법칙을 이용하면 다음과 같이 쓸 수 있습니다.

$$
\begin{align*}
	&\mathcal{E}=\frac{d\Lambda}{dt}\\
	&\rightarrow W_e=\int \frac{d\Lambda}{dt}idt=\int id\Lambda
\end{align*}
$$

이제 이동자에 가해지는 힘을 $$F_{mec}$$라고 해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/모터힘.png" alt="모터힘" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 이동자가 받는 힘)
  </figcaption>
</figure>

힘 $$F_{mec}$$가 이동자에 하는 일이 바로 출력된 역학적 에너지입니다.
다음과 같이 쓸 수 있습니다.

$$
W_{mec}=\int F_{mec}dx
$$

저장된 자기 에너지는 다음과 같이 쓸 수 있습니다.

$$
\begin{align*}
	W_m&=W_e-W_{mec}\\
	&=\int id\Lambda-\int F_{mec}dx
\end{align*}
$$

적당한 수학적 가정 하에 미소 자기 에너지는 다음과 같이 쓸 수 있습니다.

$$
dW_m=id\Lambda-F_{mec}dx
$$

이 식은 자기 에너지의 전미분입니다.
전미분은 다음과 같이 쓸 수 있습니다.

$$
dW_m=\frac{\partial W_m}{\partial\Lambda}d\Lambda+\frac{\partial W_m}{\partial x}dx
$$

각 항을 비교하면 다음과 같습니다.

$$
\begin{cases}
		&\frac{\partial W_m}{\partial\Lambda}=i\\
  &\frac{\partial W_m}{\partial x}=-F_{mec}
	\end{cases}
$$

따라서 이동자에 가해지는 힘은 다음과 같습니다.

$$
F_{mec}=-\frac{\partial W_m}{\partial x}
$$

저장된 자기 에너지를 줄이도록 힘이 가해지는 것을 알 수 있습니다.

선형 매질이라는 가정 하에 자기 에너지 식을 다시 살펴봅시다.

$$
W_m=\frac{\Lambda^2}{2L(x)}
$$

기자력에 의해 공급되는 자속은 일정합니다.
$$x$$에 따라 인덕턴스가 달라지므로 위와 같이 표기했습니다.
이 식을 이용해서 힘을 구해봅시다.

$$
\begin{align*}
		F_{mec}&=-\frac{\partial W_m}{\partial x}\\
		&=-\frac{\partial }{\partial x}\left(\frac{\Lambda^2}{2L(x)}\right)\\
		&=\frac{\Lambda^2}{2L(x)^2}\frac{dL(x)}{dx}\\
		&=\frac{1}{2}i^2\frac{dL(x)}{dx}
\end{align*}
$$

인덕턴스가 증가하도록 힘이 가해지는 것을 알 수 있습니다.
즉, 고정자 쪽으로 이동하도록 이동자에 힘이 가해집니다.

### 회전자

다음으로 이동자 대신 **회전자(Rotor)**로 동력이 전달되는 전동기를 살펴봅시다.
회전자 또한 자기 에너지를 역학적 에너지로 변환하는 부분으로, 병진 이동자와 달리 회전 운동을 합니다.

---

## 전동기의 구조

앞서 설명한 구조는 동작 원리를 설명하기 위한 것이었습니다.
실제로 쓰이는 전동기는 다음과 같은 구조입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/전동기구조실제.png" alt="전동기구조실제" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 실제 전동기의 구조)
  </figcaption>
</figure>

두 그림 모두 고정자는 전자석입니다.
회전자의 경우 왼쪽 그림에서는 자석이고, 오른쪽 그림에서는 자성체입니다.
토크는 고정자와 회전자의 상호작용을 통해 생성됩니다.
회전자가 자석인 경우, 인력이 발생합니다.
회전자가 자성체인 경우, 자기 에너지를 감소시키는 힘이 발생합니다.

---

## 회전 운동

주로 회전 운동을 하는 시스템에 대해 다룰 예정이므로, 회전 운동에 대해 설명하겠습니다.

### 각변위

**각변위(Angular Displacement)**는 변위와 비슷하게 처음의 각위치와 나중의 각위치의 차이를 나타냅니다.

$$
\Delta\theta=\theta_f-\theta_i
$$

각변위의 방향은 그림과 같이 오른손 규칙에 따라 정합니다.

<figure style="text-align: center;">
  <img src="./PEFigure/각변위.png" alt="각변위" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 각변위)
  </figcaption>
</figure>

주로 반시계 방향으로 회전하면 양수, 시계 방향으로 회전하면 음수로 둡니다.

### 각속도

**각속도(Angular Velocity)**는 속도와 비슷하게 각변위의 시간 미분입니다.

$$
\boldsymbol{\omega}=\frac{d\boldsymbol{\theta}}{dt}
$$

<figure style="text-align: center;">
  <img src="./PEFigure/각속도.png" alt="각속도" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 각속도)
  </figcaption>
</figure>

평균 각속도는 한 바퀴$$(2\pi)$$와 회전 주기에 대한 비율입니다.
주기적으로 변하며 방향성이 없는 물리량에는 스칼라로 사용할 수 있으며, 다른 말로는 **각진동수(Angular Frequency)**라고 합니다.

### 각가속도

각가속도는 각속도의 시간에 대한 변화율입니다.

$$
\boldsymbol{\alpha}=\frac{d\boldsymbol{\omega}}{dt}
$$

### 토크

**토크(Torque)**는 물체를 회전시키기 위한 힘이며, 힘(Force)와는 차원이 다른 양입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/토크.png" alt="토크" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 토크)
  </figcaption>
</figure>

$$
\mathbf{N}=\mathbf{r}\times\mathbf{F}
$$

여기서 $$\mathbf{r}$$는 회전축으로부터 작용점 사이의 변위이고, $$\mathbf{F}$$는 작용하는 힘입니다.
단위는 $$\text{N}\cdot\text{m}$$이지만 에너지의 단위인 $$\text{J}$$과는 다른 물리량이기 때문에 구분합니다.
변위와 힘 사이의 각도를 $$\theta$$라고 하면, 토크의 크기는 다음과 같습니다.

$$
N=rF\sin\theta
$$

토크 또한 뉴턴의 운동 제2법칙과 같은 형태로 표기할 수 있습니다.

$$
\mathbf{N}=J\boldsymbol{\alpha}
$$

여기서 $$\mathbf{J}$$, $$\boldsymbol{\alpha}$$는 각각 **관성 모멘트(Moment of Inertia)**, **각가속도(Angular Acceceleration)**입니다.

회전자는 토크를 받아 회전합니다.
또한 부하의 속도는 생성된 토크에 따라 달라집니다.
부하의 위치, 유량, 압력, 장력 등이 제어됩니다.

### 관성 모멘트

관성 모멘트는 회전 운동을 하는 물체가 운동 상태를 유지하려는 성질이며, **회전 관성(Inertial Moment)**이라고도 부릅니다.
다음과 같이 정의됩니다.

<figure style="text-align: center;">
  <img src="./PEFigure/관성모멘트.png" alt="관성모멘트" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 관성 모멘트)
  </figcaption>
</figure>

$$
J=\int r^2dm
$$

일반적으로 물체는 회전축이 바뀌면서 회전할 수 있습니다.
즉, 각운동량과 각속도가 일반적으로 평행이 아닙니다.

<figure style="text-align: center;">
  <img src="./PEFigure/세차운동.png" alt="세차운동" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 강체의 세차 운동)
  </figcaption>
</figure>

$$
\mathbf{L}=\mathbf{J}\boldsymbol{\omega}
$$

이때는 관성 모멘트가 아닌 **관성 텐서(Inertia Tensor)**로서 $$3\times 3$$ 행렬로 기술됩니다.
하지만 전동기의 경우, 각운동량과 각속도가 평행이므로 스칼라로 취급할 수 있습니다.

$$
\mathbf{L}=J\boldsymbol{\omega}
$$

토크는 각운동량의 시간 미분이므로 다음과 같습니다.

$$
\begin{align*}
		&\mathbf{L}=\mathbf{r}\times\mathbf{p}\\
		&\mathbf{N}=\frac{d\mathbf{L}}{dt}\\
		&\rightarrow \mathbf{N}=\mathbf{r}\times\mathbf{F}\ \ \ \text{since }\frac{d\mathbf{r}}{dt}=\mathbf{0}\ \text{(강체)},\frac{d\mathbf{p}}{dt}=\mathbf{F}
\end{align*}
$$

### 회전 운동 에너지

회전하는 물체 또한 운동 에너지를 갖습니다.
관성 모멘트를 이용하며 다음과 같이 나타낼 수 있습니다.

$$
K=\frac{1}{2}J\omega^2
$$

### 자기 모멘트

다음과 같이 전류가 흐르는 고리를 생각해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/전류고리.png" alt="전류고리" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 전류가 흐르는 고리)
  </figcaption>
</figure>

**자기 모멘트(Magnetic Moment)**는 모멘트라는 이름에서 알 수 있듯이 자기력에 의한 토크를 결정짓는 물리량입니다.
이 상황에서는 다음과 같이 쓸 수 있습니다.

$$
\mathbf{m}=iA\hat{\mathbf{n}}
$$

### 자기력에 의한 토크

다음과 같이 전류가 흐르는 고리가 자기장 내에 있다고 생각해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/전류고리자기장.png" alt="전류고리자기장" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 자기장 내의 전류가 흐르는 고리)
  </figcaption>
</figure>

외부 자기장에 의해 전류 고리가 회전합니다.
이때 토크는 다음과 같습니다.

$$
\mathbf{N}=\mathbf{m}\times\mathbf{B}
$$

자기력과 법선 벡터 사이의 각을 $$\theta$$라고 한다면, 토크의 크기는 다음과 같습니다.

$$
N=iAB\sin\theta
$$

따라서 $$\theta=90^{\circ}$$일 때, 토크의 크기가 최대가 되는 것을 알 수 있습니다.

---

## 직류 전동기

**직류 전동기(DC Motor)**는 직류 전력를 공급받아 동력을 생성하는 전동기입니다.
직류 전동기의 구조는 다음과 같습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/직류전동기.png" alt="직류전동기" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 직류 전동기)
  </figcaption>
</figure>

고정자에 감긴 권선에 전류를 흘리면 전자석이 되어 외부 자기장의 역할을 합니다.
가운데 회전자에 감긴 권선에 전류를 흘리면 자기력을 받아 회전하기 시작합니다.
하지만 반 바퀴 회전을 하면 코일에 흐르는 전류의 방향이 바뀌기 때문에 자기력을 반대 방향으로 받습니다.
따라서 전류의 방향을 유지하기 위해 **브러시(Brush)**와 **정류자(Commutator)**를 이용합니다.
정류자를 살펴보면 끊긴 부분이 있습니다.

---

## 교류 전동기

**교류 전동기(AC Motor)**는 교류 전력를 공급받아 동력을 생성하는 전동기입니다.
교류 전동기의 구조는 다음과 같습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/교류전동기.png" alt="교류전동기" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 교류 전동기)
  </figcaption>
</figure>

직류 전동기와는 달리 고정자 자석과 회전자 자석이 모두 회전하는 구조입니다.
두 자석 사이의 각이 일정하다면, 일정한 토크가 지속적으로 발생합니다.
따라서 회전자가 계속 회전할 수 있습니다.

고정자 자석의 회전은 평형 3상 전력을 공급하여 구현할 수 있습니다.
다음 그림을 살펴봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/3상자기장.png" alt="3상자기장" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 3상 전력에 의한 자기장)
  </figcaption>
</figure>

권선이 $$120^{\circ}$$ 간격으로 배치되어 3개의 전자석을 형성합니다.
이 권선에 평형 3상 전력을 공급하면 [회전하는 자기장](https://www.ece.umn.edu/users/riaz/animations/spacevecmovie.html)이 형성됩니다.

### 동기 전동기

### 유도 전동기

---

## 부하 시스템

다음 전동기 시스템을 살펴봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/전동기시스템.png" alt="전동기시스템" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 전동기 시스템)
  </figcaption>
</figure>

관성모멘트가 각각 $$J_M$$, $$J_L$$인 전동기와 부하가 커플링에 의해 연결되어 동일한 각속도로 회전합니다.
이 시스템에는 그림과 같이 두 종류의 토크가 작용합니다.
$$\mathbf{N}_M$$은 전동기 토크입니다.
전기 에너지를 받아 부하를 회전시키기 위해 작용하는 토크입니다.
$$\mathbf{N}_L$$은 부하 토크입니다.
부하 토크는 중력이나 마찰력 등의 부하를 극복하여 전동기를 구동하기 위해 필요한 토크입니다.
알짜 토크는 다음과 같이 기술됩니다.

$$
\mathbf{N}_{net}=\mathbf{N}_M-\mathbf{N}_L
$$

$$\mathbf{N}_M>\mathbf{N}_L$$이면 알짜 토크가 양수이므로 각속도가 증가합니다.
$$\mathbf{N}_M<\mathbf{N}_L$$이면 알짜 토크가 음수이므로 각속도가 감소합니다.

### 부하 시스템의 운동 방정식

총 관성 모멘트 $$J=J_M+J_L$$인 물체가 알짜 토크 $$\mathbf{N}=\mathbf{N_M}-\mathbf{N_L}$$을 받아 각가속도 $$\boldsymbol{\alpha}=\frac{d\boldsymbol{\omega}}{dt}$$로 운동합니다.
이는 다음과 같이 표현할 수 있습니다.

$$
\mathbf{N}=J\boldsymbol{\alpha}
$$

1차원 운동이므로 다음과 같이 모두 스칼라로 나타낼 수 있습니다.

$$
N=J\alpha
$$

전동기 토크는 다음과 같이 나타낼 수 있습니다.

$$
N_M=J\alpha+N_L
$$

### 마찰을 고려한 운동 방정식

다음과 같이 마찰력에 의한 토크가 작용한다고 생각해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/마찰전동기시스템.png" alt="마찰전동기시스템" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 마찰을 고려한 전동기 시스템)
  </figcaption>
</figure>

$$
-T_F=B\omega
$$

이때 알짜 토크는 다음과 같습니다.

$$
N_{net}=N_M-N_L-N_F
$$

 jifjeswoif'jsdoifjdsoifjdsoihgjiodshgdosiJFIOAEFJAOPSFJSDAOPIFJ

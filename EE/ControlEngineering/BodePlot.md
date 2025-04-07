보드 선도
=

---

## 목차
- [데시벨](#데시벨)
- [보드 선도](#bode-plot)
- [상수항의 보드 선도](#상수항의-보드-선도)
- [미분과 적분의 보드 선도](#미분과-적분의-보드-선도)

---

## 데시벨

### 벨

**벨(B, bel)**은 기준 전력에 대한 전력 비의 상용로그 값입니다.

$$
L_B=\log\left(\frac{p}{p_0}\right)\ \text{[B]}
$$

전력이 기준치 대비 $$n\text{ B}$$만큼 상승하면 $$10^n$$배 만큼 상승했다는 의미입니다.
이는 사용하기에는 매우 큰 단위입니다.

### 데시벨

벨을 대체할 다른 단위가 있습니다.
바로 **데시벨(dB, decibel)**입니다.
벨에 $$1/10$$을 의미하는 접두어 데시(deci)가 붙어서 벨에 비해 작은 단위입니다.

$$
L_{dB}=10\log\left(\frac{p}{p_0}\right)\ \text{[dB]}
$$

전력이 기준치 대비 $$n\text{ dB}$$만큼 상승하면 $$10^{n/10}$$배 만큼 상승했다는 의미입니다.

### 전압 비 및 전류 비에 대한 데시벨

전력은 다음과 같이 표현할 수 있습니다.

$$
p=vi=\frac{v^2}{R}=i^2R
$$

먼저 전압만을 이용해 데시벨을 표현하면 다음과 같습니다.

$$
\begin{align*}
		L_{dB}&=10\log\left(\frac{v^2/R}{v_0^2/R}\right)\\
		&=10\log\left(\frac{v^2}{v_0^2}\right)\\
		&=20\log\left(\frac{v}{v_0}\right)
	\end{align*}
$$

전압 비로 나타내면 계수가 $$20$$이 되는 것을 알 수 있습니다.
다음으로 전류만을 이용해 데시벨을 표현하면 다음과 같습니다.

$$
\begin{align*}
		L_{dB}&=10\log\left(\frac{i^2R}{i_0^2R}\right)\\
		&=10\log\left(\frac{i^2}{i_0^2}\right)\\
		&=20\log\left(\frac{i}{i_0}\right)
	\end{align*}
$$

전압 비와 마찬가지로 전류 비로 나타낸 데시벨 또한 계수가 $$20$$이 되는 것을 알 수 있습니다.
우리는 주로 전압 비나 전류 비를 이용할 것이기 때문에 계수가 $$20$$인 데시벨을 이용할 것입니다.

---

<h2 id="bode-plot">보드 선도</h2>

**보드 선도(Bode Plot)**는 전달 함수의 크기와 위상을 주파수 값에 따라 그래프로 나타낸 것입니다.
시스템의 주파수 응답을 분석할 때 유용하게 이용됩니다.

(Bode Plot)

### 점근적 근사

예시로 보여드린 보드 선도는 언뜻 보면 복잡해 보입니다.
이 보드 선도를 전달 함수를 통해 손으로 직접 그리는 방법 또한 있습니다.
바로 **점근적 근사(Asymptotic Approximation)**를 통해 그리는 것입니다.
시스템의 세세한 변화는 무시하고, 특정 주파수들을 중심으로 시스템의 응답이 어떻게 변화하는지 어림잡아 그리는 방법입니다.
몇 가지 가정 하에서는 정확한 보드 선도와 비교할 때, 오차가 매우 적습니다.

### 차단 주파수

앞서 보드 선도를 특정 주파수를 중심으로 어림잡아 그린다고 했습니다.
그 특정 주파수가 바로 **차단 주파수(Cut-Off Frequency)** 혹은 **코너 주파수(Corner Frequency)**라고 합니다.
이는 전력이 기준 전력 대비 절반이 되는 주파수 값입니다.

$$
\begin{align*}
		L_{dB}&=10\log\left(\frac{p}{p_0}\right)\\
        &=10\log\left(\frac{0.5p_0}{p_0}\right)\\
        &=10\log0.5\\
        &\approx-3\ \text{dB}
	\end{align*}
$$

약 $$-3\ \text{dB}$$만큼 값이 낮아집니다. 계수가 $$20$$인 데시벨 스케일로 표현하면 다음과 같습니다.

$$
\begin{align*}
		L_{dB}&=10\log0.5\\
  &=20\log\frac{1}{\sqrt{2}}
	\end{align*}
$$

이와 같이 차단 주파수는 전달 함수의 크기가 $$1/\sqrt{2}$$배가 될 때의 주파수이기도 합니다.
하지만 점근적 근사에서는 이를 무시합니다.
차단 주파수 전후로만 어떻게 변하는지 그립니다.

### 크기 스케일

다음의 전달 함수를 살펴봅시다.

$$
T(s)=\frac{K\Pi_k\left(s+z_k\right)\Pi_k\left(s^2+a_ks+b_k\right)\cdots}{\Pi_k\left(s+p_k\right)\Pi_k\left(s^2+c_ks+d_k\right)\cdots}
$$

일반적인 전달 함수는 이와 같이 1차, 2차 및 그 이상 차수에 대한 식으로 인수분해되어 나타낼 수 있습니다.
보드 선도는 주파수에 대한 응답을 분석하는 것이 목적이므로 다음과 같이 $$s=j\omega$$를 대입하여 그립니다.

$$
T(j\omega)=\frac{K\Pi_k\left(j\omega+z_k\right)\Pi_k\left(-\omega^2+ja_k\omega+b_k\right)\cdots}{\Pi_k\left(j\omega+p_k\right)\Pi_k\left(-\omega^2+jc_k\omega+d_k\right)\cdots}
$$

하지만 이렇게 곱으로 나타낸 식은 그리기 어렵습니다.
곱으로 된 식을 합으로 표현하는 방법이 있습니다.
바로 다음과 같이 로그를 취하는 것입니다.

$$
\begin{align*}
		\log\left\vert T(j\omega)\right\vert=&\ \log \left\vert K\right\vert+\sum_k\log\left\vert j\omega+z_k\right\vert+\sum_k\log\left\vert \frac{1}{j\omega+p_k}\right\vert\\
  &+\sum_k\log\left\vert-\omega^2+ja_k\omega+b_k\right\vert+\sum_k\log\left\vert\frac{1}{-\omega^2+jc_k\omega+d_k}\right\vert+\cdots
	\end{align*}
$$

이 식에 이전에 언급했듯이 $$20$$을 곱하면 데시벨 스케일로 볼 수 있습니다.

$$
\begin{align*}
		20\log\left\vert T(j\omega)\right\vert=&\ 20\log \left\vert K\right\vert+\sum_k20\log\left\vert j\omega+z_k\right\vert+\sum_k20\log\left\vert \frac{1}{j\omega+p_k}\right\vert\\
  &+\sum_k20\log\left\vert-\omega^2+ja_k\omega+b_k\right\vert+\sum_k20\log\left\vert\frac{1}{ -\omega^2+jc_k\omega+d_k}\right\vert+\cdots
\ \text{[dB]}
\end{align*}
$$

이제 각 항에 대해 그래프를 그린 뒤, 모두 더하면 원래 전달 함수의 크기에 대한 정보를 얻을 수 있습니다.

### 주파수 스케일

세로 축(크기)은 로그(데시벨)로 표현되었습니다.
가로 축은 주파수를 그대로 씁니다.
하지만 기존과 같이 선형적으로 증가하는 스케일을 쓰면 그래프를 직선으로 그릴 수 없습니다.
주파수에도 로그를 취했기 때문입니다.
따라서 일정한 간격마다 $$10$$(상용로그의 밑)배씩 증가하는 스케일을 써야 합니다.
$$10$$배를 [dec]으로 표현하고 [dB/dec]를 기울기에서 단위로 활용합니다.

### 직선의 방정식

점근적 근사를 활용할 때, 직선의 방정식을 이용하는 경우가 있습니다.
다음과 같은 직선을 생각해봅시다.

$$
20\log M=a\log\omega+b
$$

(line)

이 직선의 기울기가 $$20n\ \text{dB/dec}$$이고, 교차 주파수가 $$\omega_c$$라고 해봅시다.
교차 주파수를 이용하면 $$a$$와 $$b$$의 관계식이 다음과 같이 나타납니다.

$$
\begin{align*}
		&0=a\log\omega_c+b\\
		&b=-a\log\omega_c\\
		&20\log M=a\log\omega-a\log\omega_c=a\log\left(\frac{\omega}{\omega_c}\right)
	\end{align*}
$$

주파수가 $$10$$배 늘면 기울기 조건에 의해 크기가 $$20n\ \text{dB}$$만큼 늘어야하므로 다음과 같습니다.

\begin{align*}
		&20\log M_0=a\log\left(\frac{\omega}{\omega_c}\right)\\
		&20\log M'=a\log\left(\frac{10\omega}{\omega_c}\right)=a+a\log\left(\frac{\omega}{\omega_c}\right)=a\log\left(\frac{\omega}{\omega_c}\right)+20n\\
		&a=20n
	\end{align*}

따라서 직선의 방정식은 다음과 같습니다.

$$
20\log M=20n\log\left(\frac{\omega}{\omega_c}\right)
$$

이제 이 직선이 다음과 같이 두 점 $$\left(\omega_1,20\log M_1\right),\left(\omega_2,20\log M_2\right)$$를 지난다고 해봅시다.

(line)

두 지점간 크기의 차이는 다음과 같습니다.

$$
\begin{align*}
		&20\log M_1=20n\log\left(\frac{\omega_1}{\omega_c}\right)\\
		&20\log M_2=20n\log\left(\frac{\omega_2}{\omega_c}\right)\\
		&\Delta=20n\log\left(\frac{\omega_2}{\omega_c}\right)-20n\log\left(\frac{\omega_1}{\omega_c}\right)=20n\log\left(\frac{\omega_2}{\omega_1}\right)
	\end{align*}
$$

---

## 상수항의 보드 선도

전달 함수의 $$K$$가 실수라는 가정 하에 설명하겠습니다.
실수는 양수와 음수로 나뉩니다.
두 경우는 약간 다르게 나타납니다.

### 양수

먼저 양수입니다.

$$
F(s)=K
$$

$$s=j\omega$$를 대입하면 다음과 같습니다.

$$
\begin{align*}
		F(j\omega)&=K\\
  		&=\left\vert K\right\vert\\
		&=\left\vert K\right\vert\angle0^{\circ}
	\end{align*}
$$

나눠서 표현하면 다음과 같습니다.

$$
\begin{cases}
			20\log\left\vert F(j\omega)\right\vert=20\log\left\vert K\right\vert\\
			\angle\left\vert F(j\omega)\right\vert=0^{\circ}
		\end{cases}
$$

### 음수

다음으로 음수입니다.

$$
F(s)=K
$$

$$s=j\omega$$를 대입하면 다음과 같습니다.

$$
\begin{align*}
		F(j\omega)&=K\\
  		&=-\left\vert K\right\vert\\
		&=\left\vert K\right\vert\angle\left(-180^{\circ}\right)
	\end{align*}
$$

나눠서 표현하면 다음과 같습니다.

$$
\begin{cases}
			20\log\left\vert F(j\omega)\right\vert=20\log\left\vert K\right\vert\\
			\angle\left\vert F(j\omega)\right\vert=-180^{\circ}
		\end{cases}
$$

---

## 미분과 적분의 보드 선도

### 미분

양수 $$K_d$$에 대해 미분에 대한 식은 다음과 같습니다.

$$
F(s)=K_ds
$$

$$s=j\omega$$를 대입하면 다음과 같습니다.

$$
\begin{align*}
		F(j\omega)&=jK_d\omega\\
		&=K_d\omega\angle90^{\circ}
	\end{align*}
$$

나눠서 표현하면 다음과 같습니다.

$$
\begin{cases}
			20\log\left\vert F(j\omega)\right\vert=20\log\left(K_d\omega\right)\\
			\angle\left\vert F(j\omega)\right\vert=90^{\circ}
		\end{cases}
$$

### 적분

양수 $$K_i$$에 대해 미분에 대한 식은 다음과 같습니다.

$$
F(s)=\frac{K_i}{s}
$$

$$s=j\omega$$를 대입하면 다음과 같습니다.

$$
\begin{align*}
		F(j\omega)&=\frac{K_i}{j\omega}\\
  		&=-j\frac{K_i}{\omega}\\
		&=\frac{K_i}{\omega}\angle\left(-90^{\circ}\right)
	\end{align*}
$$

나눠서 표현하면 다음과 같습니다.

$$
\begin{cases}
			20\log\left\vert F(j\omega)\right\vert=20\log\left(\frac{K_i}{\omega}\right)\\
			\angle\left\vert F(j\omega)\right\vert=-90^{\circ}
		\end{cases}
$$

---

## 좌반면 극점과 영점의 보드 선도

### 좌반면 극점

좌반면 극점에 대한 식은 다음과 같습니다.

$$
F(s)=\frac{1}{1+\frac{s}{\omega_p}}
$$

$$s=j\omega$$를 대입하면 다음과 같습니다.

$$
\begin{align*}
		F(j\omega)&=\frac{1}{1+\frac{j\omega}{\omega_p}}\\
        &=\frac{1}{\sqrt{1+\left(\frac{\omega}{\omega_p}\right)^2}}\angle\left(-\tan^{-1}\left(\frac{\omega}{\omega_p}\right)\right)
	\end{align*}
$$

나눠서 표현하면 다음과 같습니다.

$$
\begin{cases}
			20\log\left\vert F(j\omega)\right\vert=20\log\frac{1}{\sqrt{1+\left(\frac{\omega}{\omega_p}\right)^2}}\\
			\angle\left\vert F(j\omega)\right\vert=-\tan^{-1}\left(\frac{\omega}{\omega_p}\right)
		\end{cases}
$$

우선 차단 주파수를 찾아봅시다.
크기 표현식에서 로그 속 분모가 $$\sqrt{2}$$가 돼야 합니다.
따라서 차단 주파수는 다음과 같습니다.

$$
\omega_c=\omega_p
$$

이때 크기와 위상은 다음과 같습니다.

$$
\begin{cases}
			20\log\left\vert F(j\omega_p)\right\vert=20\log\frac{1}{\sqrt{2}}=-3\ \text{dB}\\
			\angle\left\vert F(j\omega_p)\right\vert=-\tan^{-1}1=-45^{\circ}
		\end{cases}
$$

$$-3\ \text{dB}$$는 무시하기로 했고, 위상 정보는 그대로 취합니다.
따라서 다음과 같습니다.

$$
\begin{cases}
			20\log\left\vert F(j\omega_p)\right\vert=0\ \text{dB}\\
			\angle\left\vert F(j\omega_p)\right\vert=-45^{\circ}
		\end{cases}
$$

이제 차단 주파수 전후로 어떻게 근사할지 설명하겠습니다.
주파수가 차단 주파수보다 매우 작은 경우는 다음과 같습니다.

$$
\begin{cases}
			20\log\left\vert F(j\omega)\right\vert=20\log\frac{1}{\sqrt{1+0}}=0\ \text{dB}\\
			\angle\left\vert F(j\omega)\right\vert=-\tan^{-1}0=0^{\circ}
		\end{cases}\ \ \ \text{for }\omega<<\omega_c
$$

주파수가 차단 주파수보다 매우 큰 경우는 다음과 같습니다.

$$
\begin{cases}
			20\log\left\vert F(j\omega)\right\vert=20\log\frac{1}{\sqrt{\left(\frac{\omega}{\omega_p}\right)^2}}=20\log\left(\frac{\omega_p}{\omega}\right)\\
			\angle\left\vert F(j\omega)\right\vert=-\tan^{-1}\left(\frac{\omega}{\omega_p}\right)
		\end{cases}\ \ \ \text{for }\omega>>\omega_c
$$

이전에 언급했듯이 주파수 축은 $$10$$배마다 눈금을 표기합니다.
주파수가 차단 주파수보다 $$10$$배 작은 지점에서는 다음과 같습니다.

$$
\begin{cases}
			20\log\left\vert F(j0.1\omega_p)\right\vert=20\log\frac{1}{\sqrt{1+\left(\frac{0.1\omega_p}{\omega_p}\right)^2}}=-0.04\ \text{dB}\\
			\angle\left\vert F(j0.1\omega_p)\right\vert=-\tan^{-1}\left(\frac{0.1\omega_p}{\omega_p}\right)=-5.71^{\circ}
		\end{cases}
$$

이 값들을 다음과 같이 근사합니다.

$$
\begin{cases}
			20\log\left\vert F(j0.1\omega_p)\right\vert=0\ \text{dB}\\
			\angle\left\vert F(j0.1\omega_p)\right\vert=0^{\circ}
		\end{cases}
$$

이보다 작은 주파수 값에서도 동일한 값을 갖습니다.
주파수가 차단 주파수보다 $$10$$배 큰 지점에서는 다음과 같습니다.

$$
\begin{cases}
			20\log\left\vert F(j0.1\omega_p)\right\vert=20\log\frac{1}{\sqrt{1+\left(\frac{10\omega_p}{\omega_p}\right)^2}}=-20.04\ \text{dB}\\
			\angle\left\vert F(j0.1\omega_p)\right\vert=-\tan^{-1}\left(\frac{10\omega_p}{\omega_p}\right)=-84.29^{\circ}
		\end{cases}
$$

이 값들을 다음과 같이 근사합니다.

$$
\begin{cases}
			20\log\left\vert F(j0.1\omega_p)\right\vert=-20\ \text{dB}\\
			\angle\left\vert F(j0.1\omega_p)\right\vert=-90^{\circ}
		\end{cases}
$$

이보다 큰 주파수 값에서는 크기의 경우, 계속 감소하고, 위상은 동일합니다.
크기는 주파수가 $$10$$배 늘어날 때마다 $$20\ \text{dB}$$씩 떨어집니다.
이럴 때 기울기는 $$-20\ \text{dB/dec}$$라고 하거나 간단히 $$-1$$이라고 합니다.
차단 주파수 미만의 주파수에서는 값이 $$0\ \text{dB}$$입니다.
위상은 차단 주파수의 $$0.1$$배부터 $$10$$배까지 $$-45^{\circ}\text{/dec}$$의 기울기를 갖고, 양 끝에서는 각각 $$0^{\circ}$$와 	$$-90^{\circ}$$입니다.
이러한 규칙을 가지고 좌반면 극점의 보드 선도를 다음과 같이 그릴 수 있습니다.

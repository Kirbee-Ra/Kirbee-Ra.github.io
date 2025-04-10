수동 필터
=

---

## 목차

- [수동 필터]
- [수동 소자의 주파수 응답]
- [1차 저역 필터]
- [1차 고역 필터]
- [RLC 회로]
- [2차 대역 필터]
- [2차 대역 차단 필터]

---

## 수동 필터

수동 소자로만 구성된 필터인 **수동 필터(Passive Filter)**에 대해 설명하겠습니다.

---

## 수동 소자의 주파수 응답

수동 필터를 설계하기 전에 수동 소자가 주파수에 대해 어떤 응답 특성을 갖는지 알아야 합니다.

### 저항

저항의 임피던스는 다음과 같습니다.

$$
Z_R=R
$$

임피던스가 주파수와 무관합니다.
따라서 주파수에 상관 없이 신호를 통과시키는 것을 알 수 있습니다.

### 축전기

축전기의 임피던스는 다음과 같습니다.

$$
Z_C=\frac{1}{j\omega C}
$$

임피던스가 주파수에 반비례하는 것을 알 수 있습니다.
저주파 신호에 대해서는 개방된 것으로 보이고, 고주파 신호에 대해서는 단락된 것으로 보입니다.
따라서 축전기는 저주파 신호를 막고, 고주파 신호를 통과시키는 것을 알 수 있습니다.

### 인덕터

인덕터의 임피던스는 다음과 같습니다.

$$
Z_L=j\omega L
$$

임피던스가 주파수에 비례하는 것을 알 수 있습니다.
저주파 신호에 대해서는 단락된 것으로 보이고, 고주파 신호에 대해서는 개방된 것으로 보입니다.
따라서 인덕터는 저주파 신호를 통과시키고, 고주파 신호를 막는 것을 알 수 있습니다.

---

## 차단 주파수

실제 필터 회로는 이상적인 필터처럼 구성할 수 없습니다.
그렇다면 통과 대역과 차단 대역을 구분짓는 기준이 있어야 합니다.
이 기준을 **차단 주파수(Cut-Off Frequency)**라고 합니다.
차단 주파수는 전달 함수의 크기가 $$\displaystyle\frac{1}{\sqrt{2}}$$배로 줄어드는 주파수입니다.

$$
\left\vert H(j\omega_c)\right\vert=\frac{1}{\sqrt{2}}\left\vert H\right\vert_{max}
$$

이 차단 주파수는 평균 전력이 최댓값의 절반이 되는 주파수로도 정의할 수 있습니다.
전력이 절반이 되었다는 것은 전압 비나 전류 비가 $$\displaystyle\frac{1}{\sqrt{2}}$$배가 되었다는 의미입니다.

수동 필터는 증폭을 할 수 없으므로 전달 함수의 크기의 최댓값은 $$1$$입니다.
차단 주파수에서의 전달 함수의 크기를 데시벨 스케일로 나타내면 다음과 같습니다.

$$
\begin{align*}
			&\left\vert H(j\omega_c)\right\vert=\frac{1}{\sqrt{2}}\\
			&\rightarrow20\log\left\vert H(j\omega_c)\right\vert=-3\ \text{dB}
	\end{align*}
$$

이때 위상의 경우는 필터의 차수에 따라 다릅니다.
1차 필터는 주파수에 대한 항이 1차항으로 나타납니다.
2차 필터는 주파수에 대한 항이 2차항으로 나타납니다.
이는 각 부분에서 자세히 다루겠습니다.

---

## 1차 저역 필터

**저역 필터(Low Pass Filter, LPF)**는 **저주파 통과 필터**라고도 하며, 저주파 신호만 출력되게 하는 필터입니다.

### LPF RC 회로

다음과 같은 RC 회로를 살펴봅시다.

(RC)

각 소자에 걸리는 전압은 전압 분배에 의해 다음과 같습니다.

$$
\begin{cases}
			\mathbf{V}_R=\frac{R}{R+1/j\omega C}\mathbf{V}_{in}\\
			\mathbf{V}_C=\frac{1/j\omega C}{R+1/j\omega C}\mathbf{V}_{in}
		\end{cases}
$$

위 식을 통해 저주파 대역에서는 축전기에 걸리는 전압이 더 크고, 고주파 대역에서는 저항에 걸리는 전압이 더 큰 것을 알 수 있습니다.
따라서 저주파 신호만을 출력하려면 축전기에 걸린 전압을 출력 전압으로 이용하면 됩니다.

전압 비는 다음과 같습니다.

$$
\begin{align*}
			H(j\omega)&=\frac{1/j\omega C}{R+1/j\omega C}\\
			&=\frac{1/\left(RC\right)^2}{\sqrt{\omega^2+\left(1/RC\right)^2}}\angle\left(-\tan^{-1}\left(\omega RC\right)\right)
	\end{align*}
$$

차단 주파수는 다음과 같이 구할 수 있습니다.

$$
\begin{align*}
			&\frac{1}{2}=\frac{1/\left(RC\right)^2}{\sqrt{\omega_c^2+\left(1/RC\right)^2}}\\
			&\rightarrow\omega_c=\frac{1}{RC}
	\end{align*}
$$

차단 주파수에서의 위상은 다음과 같습니다.

$$
\begin{align*}
			\angle\left(-\tan^{-1}\left(\omega_c RC\right)\right)&=\angle\left(-\tan^{-1}1\right)\\
			&=-45^{\circ}
	\end{align*}
$$

보드 선도를 통해 다음과 같이 나타낼 수 있습니다.

(BP)

### LPF RL 회로

다음과 같은 RL 회로를 살펴봅시다.

(RL)

각 소자에 걸리는 전압은 전압 분배에 의해 다음과 같습니다.

$$
\begin{cases}
			\mathbf{V}_R=\frac{R}{R+j\omega L}\mathbf{V}_{in}\\
			\mathbf{V}_L=\frac{j\omega L}{R+j\omega L}\mathbf{V}_{in}
		\end{cases}
$$

위 식을 통해 저주파 대역에서는 저항에 걸리는 전압이 더 크고, 고주파 대역에서는 인덕터에 걸리는 전압이 더 큰 것을 알 수 있습니다.
따라서 저주파 신호만을 출력하려면 저항에 걸린 전압을 출력 전압으로 이용하면 됩니다.

전압 비는 다음과 같습니다.

$$
\begin{align*}
			H(j\omega)&=\frac{j\omega L}{R+j\omega L}\\
			&=\frac{\left(R/L\right)^2}{\sqrt{\omega^2+\left(R/L\right)^2}}\angle\left(-\tan^{-1}\left(\frac{\omega L}{R}\right)\right)
	\end{align*}
$$

차단 주파수는 다음과 같이 구할 수 있습니다.

$$
\begin{align*}
			&\frac{1}{2}=\frac{\left(R/L\right)^2}{\sqrt{\omega_c^2+\left(R/L\right)^2}}\\
			&\rightarrow\omega_c=\frac{R}{L}
	\end{align*}
$$

차단 주파수에서의 위상은 다음과 같습니다.

$$
	\begin{align*}
			\angle\left(-\tan^{-1}\left(\frac{\omega_c L}{R}\right)\right)&=\angle\left(-\tan^{-1}1\right)\\
			&=-45^{\circ}
	\end{align*}
$$

보드 선도를 통해 다음과 같이 나타낼 수 있습니다.

(BP)

---

## 1차 고역 필터

**고역 필터(High Pass Filter, HPF)**는 **고주파 통과 필터**라고도 하며, 고주파 신호만 출력되게 하는 필터입니다.

### HPF RC 회로

다음과 같은 RC 회로를 살펴봅시다.

(RC)

각 소자에 걸리는 전압은 전압 분배에 의해 다음과 같습니다.

$$
\begin{cases}
			\mathbf{V}_R=\frac{R}{R+1/j\omega C}\mathbf{V}_{in}\\
			\mathbf{V}_C=\frac{1/j\omega C}{R+1/j\omega C}\mathbf{V}_{in}
		\end{cases}
$$

위 식을 통해 고주파 대역에서는 저항에 걸리는 전압이 더 크고, 저주파 대역에서는 축전기에 걸리는 전압이 더 큰 것을 알 수 있습니다.
따라서 고주파 신호만을 출력하려면 저항에 걸린 전압을 출력 전압으로 이용하면 됩니다.

### HPF RL 회로

다음과 같은 RL 회로를 살펴봅시다.

(RL)

각 소자에 걸리는 전압은 전압 분배에 의해 다음과 같습니다.

$$
\begin{cases}
			\mathbf{V}_R=\frac{R}{R+j\omega L}\mathbf{V}_{in}\\
			\mathbf{V}_L=\frac{j\omega L}{R+j\omega L}\mathbf{V}_{in}
		\end{cases}
$$

위 식을 통해 고주파 대역에서는 인덕터에 걸리는 전압이 더 크고, 저주파 대역에서는 저항에 걸리는 전압이 더 큰 것을 알 수 있습니다.
따라서 저주파 신호만을 출력하려면 인덕터에 걸린 전압을 출력 전압으로 이용하면 됩니다.

---

## RLC 회로

저항, 축전기, 인덕터를 모두 이용하는 2차 필터를 설명하기 전에 RLC 회로의 동작을 간단하게 설명하겠습니다.

### RLC 직렬 회로

먼저 RLC 직렬 회로입니다.
세 소자가 모두 직렬로 연결되어 있습니다.


### RLC 병렬 회로

---

## 2차 대역 필터

### BPF 직렬 RLC 회로

### BPF 병렬 RLC 회로

---

## 2차 대역 차단 필터

### BSF 직렬 RLC 회로

### BSF 병렬 RLC 회로

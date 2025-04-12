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

## 1차 저역 필터

**저역 필터(Low Pass Filter, LPF)**는 **저주파 통과 필터**라고도 하며, 저주파 신호만 출력하는 필터입니다.

### LPF RC 회로

다음과 같은 RC 회로를 살펴봅시다.

(RC)

저주파 대역에서는 축전기가 개방되어 보이고, 고주파 대역에서는 축전기가 단락되어 보입니다.
직렬 연결된 소자는 임피던스 크기가 큰 쪽이 지배적이므로, 저주파 대역에서는 축전기에 걸리는 전압이 더 큽니다.
따라서 저주파 신호만을 출력하려면 축전기에 걸린 전압을 출력 전압으로 이용하면 됩니다.

$$
	\begin{align*}
&V_C(s)=\displaystyle\frac{\displaystyle\frac{1}{sC}}{R+\displaystyle\frac{1}{sC}}V_{in}(s)\\
&H(s)=\displaystyle\frac{\displaystyle\frac{1}{sC}}{R+\displaystyle\frac{1}{sC}}\\
&H(j\omega)=\displaystyle\frac{\displaystyle\frac{1}{j\omega C}}{R+\displaystyle\frac{1}{j\omega C}}
	\end{align*}
$$

전압 비는 다음과 같습니다.

$$
\begin{align*}
	H(j\omega)&=\frac{\displaystyle\frac{1}{j\omega C}}{R+\displaystyle\frac{1}{j\omega C}}\\
	&=\frac{\displaystyle\frac{1}{\left(RC\right)^2}}{\sqrt{\omega^2+\displaystyle\frac{1}{\left(RC\right)^2}}}\angle\left(-\tan^{-1}\left(\omega RC\right)\right)
\end{align*}
$$

차단 주파수는 다음과 같이 구할 수 있습니다.

$$
\begin{align*}
			&\frac{1}{\sqrt{2}}=\frac{\displaystyle\frac{1}{\left(RC\right)^2}}{\sqrt{\omega^2+\displaystyle\frac{1}{\left(RC\right)^2}}}\\
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

저주파 대역에서는 인덕터가 단락되어 보이고, 고주파 대역에서는 인덕터가 개방되어 보입니다.
직렬 연결된 소자는 임피던스 크기가 큰 쪽이 지배적이므로, 저주파 대역에서는 저항에 걸리는 전압이 더 큽니다.
따라서 저주파 신호만을 출력하려면 저항에 걸린 전압을 출력 전압으로 이용하면 됩니다.

$$
	\begin{align*}
	&V_R(s)=\displaystyle\frac{R}{R+sL}V_{in}(s)\\
	&H(s)=\displaystyle\frac{R}{R+sL}\\
	&H(j\omega)=\displaystyle\frac{R}{R+j\omega L}
\end{align*}
$$

전압 비는 다음과 같습니다.

$$
	\begin{align*}
	H(j\omega)&=\displaystyle\frac{R}{R+j\omega L}\\
	&=\frac{\left(\displaystyle\frac{R}{L}\right)^2}{\sqrt{\omega^2+\left(\displaystyle\frac{R}{L}\right)^2}}\angle\left(-\tan^{-1}\left(\frac{\omega L}{R}\right)\right)
\end{align*}
$$

차단 주파수는 다음과 같이 구할 수 있습니다.

$$
\begin{align*}
			&\frac{1}{\sqrt{2}}=\frac{\left(\displaystyle\frac{R}{L}\right)^2}{\sqrt{\omega^2+\left(\displaystyle\frac{R}{L}\right)^2}}\\
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

### 일반적인 1차 저역 필터

앞서 살펴봤듯이 일반적인 1차 저역 필터의 전달 함수는 다음과 같은 형태입니다.

$$
	\begin{align*}
		H(s)=\frac{A\omega_c}{s+\omega_c}
	\end{align*}
$$

수동 필터의 경우는 증폭 비가 $$1$$이므로 다음과 같습니다.

$$
	\begin{align*}
		H(s)=\frac{\omega_c}{s+\omega_c}
	\end{align*}
$$

크기와 위상은 다음과 같습니다.

$$
	\begin{align*}
		H(j\omega)&=\frac{\omega_c}{j\omega+\omega_c}\\
		&=\frac{\omega_c}{\sqrt{\omega^2+\omega_c^2}}\angle\left(-\tan^{-1}\left(\frac{\omega}{\omega_c}\right)\right)
	\end{align*}
$$

차단 주파수에서 위상은 다음과 같습니다.

$$
	\begin{align*}
	\angle\left(-\tan^{-1}\left(\frac{\omega_c}{\omega_c}\right)\right)&=\angle\left(-\tan^{-1}1\right)\\
	&=-45^{\circ}
\end{align*}
$$

보드 선도는 다음과 같이 나타납니다.

(BP)

---

## 1차 고역 필터

**고역 필터(High Pass Filter, HPF)**는 **고주파 통과 필터**라고도 하며, 고주파 신호만 출력하는 필터입니다.

### HPF RC 회로

다음과 같은 RC 회로를 살펴봅시다.

(RC)

저주파 대역에서는 축전기가 개방되어 보이고, 고주파 대역에서는 축전기가 단락되어 보입니다.
직렬 연결된 소자는 임피던스 크기가 큰 쪽이 지배적이므로, 고주파 대역에서는 저항에 걸리는 전압이 더 큽니다.
따라서 고주파 신호만을 출력하려면 저항에 걸린 전압을 출력 전압으로 이용하면 됩니다.

$$
	\begin{align*}
&V_R(s)=\displaystyle\frac{R}{R+\displaystyle\frac{1}{sC}}V_{in}(s)\\
&H(s)=\displaystyle\frac{R}{R+\displaystyle\frac{1}{sC}}\\
&H(j\omega)=\displaystyle\frac{R}{R+\displaystyle\frac{1}{j\omega C}}
\end{align*}
$$

전압 비는 다음과 같습니다.

$$
	\begin{align*}
	H(j\omega)&=\displaystyle\frac{R}{R+\displaystyle\frac{1}{j\omega C}}\\
	&=\frac{\omega}{\sqrt{\omega^2+\left(\displaystyle\frac{1}{RC}\right)^2}}\angle\left(\tan^{-1}\left(\frac{1}{\omega RC}\right)\right)
\end{align*}
$$

차단 주파수는 다음과 같이 구할 수 있습니다.

$$
	\begin{align*}
&\frac{1}{\sqrt{2}}=\frac{\omega_c}{\sqrt{\omega_c^2+\left(\displaystyle\frac{1}{RC}\right)^2}}\\
&\rightarrow\omega_c=\frac{1}{RC}
\end{align*}
$$

차단 주파수에서의 위상은 다음과 같습니다.

$$
\begin{align*}
	\angle\left(\tan^{-1}\left(\frac{1}{\omega_c RC}\right)\right)&=\angle\left(\tan^{-1}1\right)\\
	&=45^{\circ}
\end{align*}
$$

보드 선도를 통해 다음과 같이 나타낼 수 있습니다.

(BP)

### HPF RL 회로

다음과 같은 RL 회로를 살펴봅시다.

(RL)

저주파 대역에서는 인덕터가 단락되어 보이고, 고주파 대역에서는 인덕터가 개방되어 보입니다.
직렬 연결된 소자는 임피던스 크기가 큰 쪽이 지배적이므로, 고주파 대역에서는 인덕터에 걸리는 전압이 더 큽니다.
따라서 고주파 신호만을 출력하려면 인덕터에 걸린 전압을 출력 전압으로 이용하면 됩니다.

$$
	\begin{align*}
&V_L(s)=\displaystyle\frac{sL}{R+sL}V_{in}(s)\\
&H(s)=\displaystyle\frac{sL}{R+sL}\\
&H(j\omega)=\displaystyle\frac{j\omega L}{R+j\omega L}
\end{align*}
$$

전압 비는 다음과 같습니다.

$$
\begin{align*}
	H(j\omega)&=\displaystyle\frac{j\omega L}{R+j\omega L}\\
	&=\frac{\omega}{\sqrt{\omega^2+\left(\displaystyle\frac{R}{L}\right)^2}}\angle\left(\tan^{-1}\left( \frac{R}{\omega L}\right)\right)
\end{align*}
$$

차단 주파수는 다음과 같이 구할 수 있습니다.

$$
	\begin{align*}
&\frac{1}{\sqrt{2}}=\frac{\omega}{\sqrt{\omega^2+\left(\displaystyle\frac{R}{L}\right)^2}}\\
&\rightarrow\omega_c=\frac{R}{L}
\end{align*}
$$

차단 주파수에서의 위상은 다음과 같습니다.

$$
\begin{align*}
\angle\left(\tan^{-1}\left( \frac{R}{\omega_c L}\right)\right)&=\angle\left(\tan^{-1}1\right)\\
	&=45^{\circ}
\end{align*}
$$

보드 선도를 통해 다음과 같이 나타낼 수 있습니다.

(BP)

### 일반적인 1차 고역 필터

앞서 살펴봤듯이 일반적인 1차 저역 필터의 전달 함수는 다음과 같은 형태입니다.

$$
	\begin{align*}
		H(s)=\frac{As}{s+\omega_c}
	\end{align*}
$$

수동 필터의 경우는 증폭 비가 $$1$$이므로 다음과 같습니다.

$$
	\begin{align*}
		H(s)=\frac{s}{s+\omega_c}
	\end{align*}
$$

크기와 위상은 다음과 같습니다.

$$
	\begin{align*}
	H(j\omega)&=\frac{j\omega}{j\omega+\omega_c}\\
	&=\frac{\omega}{\sqrt{\omega^2+\omega_c^2}}\angle\left(\tan^{-1}\left(\frac{\omega_c}{\omega}\right)\right)
\end{align*}
$$

차단 주파수에서 위상은 다음과 같습니다.

$$
	\begin{align*}
\angle\left(\tan^{-1}\left(\frac{\omega_c}{\omega_c}\right)\right)&=\angle\left(\tan^{-1}1\right)\\
&=45^{\circ}
\end{align*}
$$

보드 선도는 다음과 같이 나타납니다.

(BP)

---

## 2차 대역 필터

**대역 필터(Band Pass Filter, BPF)**는 특정 주파수 대역만 출력하는 필터입니다.
2차 대역 필터는 저항, 축전기, 인덕터로 구성됩니다.

### BPF 직렬 RLC 회로

먼저 RLC 직렬 필터 회로입니다.
세 소자가 모두 직렬로 연결되어 있습니다.

저주파 대역에서는 축전기가 단락되어 보이고, 고주파 대역에서는 인덕터가 단락되어 보입니다.
그러므로 두 대역의 신호는 통과하기 어렵습니다.
중간 대역에서는 축전기와 인덕터의 임피던스가 상쇄하게 되어 임피던스가 저항 값에 가까워집니다.
따라서 대역 필터를 구성하려면, 저항에 걸리는 전압을 출력해야 합니다.

$$
	\begin{align*}
&V_R(s)=\frac{R}{sL+R+\displaystyle\frac{1}{sC}}V_{in}(s)\\
&H(s)=\frac{R}{sL+R+\displaystyle\frac{1}{sC}}\\
&H(j\omega)=\frac{R}{j\omega L+R+\displaystyle\frac{1}{j\omega C}}
\end{align*}
$$

전압 비는 다음과 같습니다.

$$
\begin{align*}
	H(j\omega)&=\frac{R}{j\omega L+R+\displaystyle\frac{1}{j\omega C}}\\
	&=\frac{\omega\displaystyle\frac{R}{L}}{\sqrt{\left(\displaystyle\frac{1}{LC}-\omega^2\right)^2+\left(\omega\displaystyle\frac{R}{L}\right)^2}}\angle\left(\tan^{-1}\left(\frac{1-\omega^2LC}{\omega RC}\right)\right)
\end{align*}
$$

차단 주파수는 다음과 같이 구할 수 있습니다.

$$
	\begin{align*}
	&\frac{1}{\sqrt{2}}=\frac{\omega_c\displaystyle\frac{R}{L}}{\sqrt{\left(\displaystyle\frac{1}{LC}-\omega_c^2\right)^2+\left(\omega_c\displaystyle\frac{R}{L}\right)^2}}\\
	&2=\left(\frac{1}{LC}-\omega_c^2\right)^2\left(\frac{L}{\omega_c R}\right)^2+1\\
	&\frac{1}{LC}-\omega_c^2=\pm\omega_c\frac{R}{L}\\
	&\omega_c=\mp\frac{R}{2L}+\sqrt{\left(\frac{R}{2L}\right)^2+\frac{1}{LC}}
\end{align*}
$$

차단 주파수에서의 위상은 다음과 같습니다.

$$
\begin{align*}
	\angle\left(\tan^{-1}\left(\frac{1-\omega_c^2LC}{\omega_cRC}\right)\right)&=\angle\left(\tan^{-1}\left(\pm1\right)\right)\\
	&=\pm45^{\circ}
\end{align*}
$$

공진 주파수는 다음과 같습니다.

$$
	\begin{align*}
\omega_0&=\sqrt{\omega_{c1}\omega_{c2}}\\
&=\frac{1}{\sqrt{LC}}
\end{align*}
$$

대역폭은 다음과 같습니다.

$$
	\begin{align*}
\beta&=\omega_{c2}-\omega_{c1}\\
&=\frac{R}{L}
\end{align*}
$$

$$Q$$ 인자는 다음과 같습니다.

$$
	\begin{align*}
Q&=\frac{\omega_0}{\beta}\\
&=\frac{1}{R}\sqrt{\frac{L}{C}}
\end{align*}
$$

보드 선도를 통해 다음과 같이 나타낼 수 있습니다.

(BP)


### BPF 병렬 RLC 회로

다음은 RLC 병렬 필터 회로입니다.
축전기와 인덕터는 병렬로 연결되어 있고, 이들의 등가 임피던스는 저항과 직렬로 연결되어 있습니다.

병렬로 연결된 임피던스는 크기가 작은 쪽이 지배적입니다.
병렬로 연결된 두 소자는 저주파일 때와 고주파일 때 둘 다 임피던스가 낮습니다.
그러므로 두 대역의 주파수를 지닌 신호는 크기가 비교적 작아집니다.
반면에 중간 대역에서는 임피던스가 매우 커집니다.
따라서 대역 필터를 구성하려면, 병렬로 연결된 두 소자에 걸리는 전압을 출력해야 합니다.

$$
	\begin{align*}
	&V_X(s)=\frac{sL\vert\vert\displaystyle\frac{1}{sC}}{R+\left(sL\vert\vert\displaystyle\frac{1}{sC}\right)}V_{in}(s)\\
	&H(s)=\frac{sL\vert\vert\displaystyle\frac{1}{sC}}{R+\left(sL\vert\vert\displaystyle\frac{1}{sC}\right)}=\frac{\displaystyle\frac{1}{R}}{sC+\displaystyle\frac{1}{R}+\displaystyle\frac{1}{sL}}\\
	&H(j\omega)=\frac{\displaystyle\frac{1}{R}}{j\omega C+\displaystyle\frac{1}{R}+\displaystyle\frac{1}{j\omega L}}
\end{align*}
$$

전압 비는 다음과 같습니다.

$$
\begin{align*}
	H(j\omega)&=\frac{\displaystyle\frac{1}{R}}{j\omega C+\displaystyle\frac{1}{R}+\displaystyle\frac{1}{j\omega L}}\\
	&=\frac{\omega\displaystyle\frac{1}{RC}}{\sqrt{\left(\displaystyle\frac{1}{LC}-\omega^2\right)^2+\left(\omega\displaystyle\frac{1}{RC}\right)^2}}\angle\left(\tan^{-1}\left(\frac{1-\omega^2LC}{\omega\displaystyle\frac{L}{R}}\right)\right)
\end{align*}
$$

차단 주파수는 다음과 같이 구할 수 있습니다.

$$
	\begin{align*}
	&\frac{1}{\sqrt{2}}=\frac{\omega_c\displaystyle\frac{1}{RC}}{\sqrt{\left(\displaystyle\frac{1}{LC}-\omega_c^2\right)^2+\left(\omega_c\displaystyle\frac{1}{RC}\right)^2}}\\
	&2=\left(\frac{1}{LC}-\omega_c^2\right)^2\left(\frac{RC}{\omega_c}\right)^2+1\\
	&\frac{1}{LC}-\omega_c^2=\pm\omega_c\frac{1}{RC}\\
	&\omega_c=\mp\frac{1}{2RC}+\sqrt{\left(\frac{1}{2RC}\right)^2+\frac{1}{LC}}
\end{align*}
$$

차단 주파수에서의 위상은 다음과 같습니다.

$$
\begin{align*}
	\angle\left(\tan^{-1}\left(\frac{1-\omega_c^2LC}{\omega_c\displaystyle\frac{L}{R}}\right)\right)&=\angle\left(\tan^{-1}\left(\pm1\right)\right)\\
	&=\pm45^{\circ}
\end{align*}
$$

공진 주파수는 다음과 같습니다.

$$
	\begin{align*}
\omega_0&=\sqrt{\omega_{c1}\omega_{c2}}\\
&=\frac{1}{\sqrt{LC}}
\end{align*}
$$

대역폭은 다음과 같습니다.

$$
	\begin{align*}
\beta&=\omega_{c2}-\omega_{c1}\\
&=\frac{1}{RC}
\end{align*}
$$

$$Q$$ 인자는 다음과 같습니다.

$$
	\begin{align*}
Q&=\frac{\omega_0}{\beta}\\
&=R\sqrt{\frac{C}{L}}
\end{align*}
$$

보드 선도를 통해 다음과 같이 나타낼 수 있습니다.

(BP)

### 일반적인 대역 필터

앞서 살펴봤듯이 일반적인 2차 대역 필터의 전달 함수는 다음과 같은 형태입니다.

$$
	\begin{align*}
		H(s)=\frac{\beta s}{s^2+\beta s+\omega_0^2}
	\end{align*}
$$

크기와 위상은 다음과 같습니다.

$$
	\begin{align*}
	H(j\omega)&=\frac{\beta}{j\omega+\beta+\displaystyle\frac{\omega_0^2}{j\omega}}\\
	&=\frac{\beta}{\sqrt{\beta^2+\left(\displaystyle\frac{\omega^2-\omega_0^2}{\omega}\right)^2}}\angle\left(\tan^{-1}\left(\frac{\omega_0^2-\omega^2}{\beta\omega}\right)\right)
\end{align*}
$$

차단 주파수는 다음과 같습니다.

$$
\begin{align*}
	&\frac{1}{\sqrt{2}}=\frac{\beta}{\sqrt{\beta^2+\left(\displaystyle\frac{\omega_c^2-\omega_0^2}{\omega_c}\right)^2}}\\
	&\beta^2+\left(\frac{\omega_c^2-\omega_0^2}{\omega_c}\right)^2=2\beta^2\\
	&\frac{\omega_c^2-\omega_0^2}{\omega_c}=\pm\beta\\
	&\omega_c=\mp\frac{\beta}{2}+\sqrt{\left(\frac{\beta}{2}\right)^2+\omega_0^2}
\end{align*}
$$

차단 주파수에서 위상은 다음과 같습니다.

$$
	\begin{align*}
\angle\left(\tan^{-1}\left(\frac{\omega_0^2-\omega^2}{\beta\omega}\right)\right)&=\angle\left(\tan^{-1}\left(\pm1\right)\right)\\
&=\pm45^{\circ}
\end{align*}
$$

보드 선도는 다음과 같이 나타납니다.

(BP)

---

## 2차 대역 차단 필터

**대역 차단 필터(Band Stop Filter, BSF)**는 특정 주파수 대역만 차단하는 필터입니다.
2차 대역 차단 필터는 저항, 축전기, 인덕터로 구성됩니다.

### BSF 직렬 RLC 회로

먼저 RLC 직렬 필터 회로입니다.
세 소자가 모두 직렬로 연결되어 있습니다.

이번에는 그림과 같이 소자의 배치를 바꿔봅시다.
이전에 언급했듯이 저주파 대역에서는 축전기가 단락되어 보이고, 고주파 대역에서는 인덕터가 단락되어 보입니다.
출력을 축전기와 인덕터를 직렬 연결한 부분에 설정하면, 중간 대역에서 임피던스가 매우 작아져서 해당 대역의 주파수를 지닌 신호는 크기가 비교적 작아집니다.
따라서 대역 차단 필터를 구성하려면, 축전기와 인덕터를 직렬 연결한 부분에 걸리는 전압을 출력해야 합니다.

$$
	\begin{align*}
	&V_X(s)=\frac{sL+\displaystyle\frac{1}{sC}}{sL+R+\displaystyle\frac{1}{sC}}V_{in}(s)\\
	&H(s)=\frac{sL+\displaystyle\frac{1}{sC}}{sL+R+\displaystyle\frac{1}{sC}}\\
	&H(j\omega)=\frac{j\omega L+\displaystyle\frac{1}{j\omega C}}{j\omega L+R+\displaystyle\frac{1}{j\omega C}}
\end{align*}
$$

전압 비는 다음과 같습니다.

$$
\begin{align*}
	H(j\omega)&=\frac{j\omega L+\displaystyle\frac{1}{j\omega C}}{j\omega L+R+\displaystyle\frac{1}{j\omega C}}\\
	&=\frac{\left\vert1-\omega^2LC\right\vert}{\sqrt{\left(1-\omega^2LC\right)^2+\left(\omega RC\right)^2}}\angle\left(-\tan^{-1}\left(\frac{\omega RC}{1-\omega^2LC}\right)\right)
\end{align*}
$$

차단 주파수는 다음과 같이 구할 수 있습니다.

$$
\begin{align*}
&\frac{1}{\sqrt{2}}=\frac{\left\vert1-\omega_c^2LC\right\vert}{\sqrt{\left(1-\omega_c^2LC\right)^2+\left(\omega_c RC\right)^2}}\\
&\left(1-\omega_c^2LC\right)^2+\left(\omega_c RC\right)^2=2\left(1-\omega_c^2LC\right)^2\\
&1-\omega_c^2LC=\pm\omega_c RC\\
&\omega_c=\mp\frac{R}{2L}+\sqrt{\left(\frac{R}{2L}\right)^2+\frac{1}{LC}}
\end{align*}
$$

차단 주파수에서의 위상은 다음과 같습니다.

$$
	\begin{align*}
\angle\left(-\tan^{-1}\left(\frac{\omega RC}{1-\omega^2LC}\right)\right)&=\angle\left(-\tan^{-1}\left(\pm1\right)\right)\\
&=\mp45^{\circ}
\end{align*}
$$

공진 주파수는 다음과 같습니다.

$$
	\begin{align*}
\omega_0&=\sqrt{\omega_{c1}\omega_{c2}}\\
&=\frac{1}{\sqrt{LC}}
\end{align*}
$$

대역폭은 다음과 같습니다.

$$
	\begin{align*}
\beta&=\omega_{c2}-\omega_{c1}\\
&=\frac{R}{L}
\end{align*}
$$

$$Q$$ 인자는 다음과 같습니다.

$$
	\begin{align*}
Q&=\frac{\omega_0}{\beta}\\
&=\frac{1}{R}\sqrt{\frac{L}{C}}
\end{align*}
$$

보드 선도를 통해 다음과 같이 나타낼 수 있습니다.

(BP)

### BSF 병렬 RLC 회로

다음은 RLC 병렬 필터 회로입니다.
축전기와 인덕터는 병렬로 연결되어 있고, 이들의 등가 임피던스는 저항과 직렬로 연결되어 있습니다.

직렬로 연결된 임피던스는 크기가 큰 쪽이 지배적입니다.
중간 대역에서는 병렬로 연결된 두 소자의 등가 임피던스가 지배적입니다.
저주파 대역과 고주파 대역에서는 저항이 지배적입니다.
따라서 대역 차단 필터를 구성하려면, 저항에 걸리는 전압을 출력해야 합니다.

$$
	\begin{align*}
	&V_X(s)=\frac{R}{R+\left(sL\vert\vert\displaystyle\frac{1}{sC}\right)}V_{in}(s)\\
	&H(s)=\frac{R}{R+\left(sL\vert\vert\displaystyle\frac{1}{sC}\right)}=\frac{sC+\displaystyle\frac{1}{sL}}{sC+\displaystyle\frac{1}{R}+\displaystyle\frac{1}{sL}}\\
	&H(j\omega)=\frac{j\omega C+\displaystyle\frac{1}{j\omega L}}{j\omega C+\displaystyle\frac{1}{R}+\displaystyle\frac{1}{j\omega L}}
\end{align*}
$$

전압 비는 다음과 같습니다.

$$
	\begin{align*}
	H(j\omega)&=\frac{j\omega C+\displaystyle\frac{1}{j\omega L}}{j\omega C+\displaystyle\frac{1}{R}+\displaystyle\frac{1}{j\omega L}}\\
	&=\frac{\left\vert1-\omega^2LC\right\vert}{\sqrt{\left(1-\omega^2LC\right)^2+\left(\omega\displaystyle\frac{L}{R}\right)^2}}\angle\left(-\tan^{-1}\left(\frac{\omega\displaystyle\frac{L}{R}}{1-\omega^2LC}\right)\right)
\end{align*}
$$

차단 주파수는 다음과 같이 구할 수 있습니다.

$$
	\begin{align*}
	&\frac{1}{\sqrt{2}}=\frac{\left\vert1-\omega_c^2LC\right\vert}{\sqrt{\left(1-\omega_c^2LC\right)^2+\left(\omega_c\displaystyle\frac{L}{R}\right)^2}}\\
	&\left(1-\omega_c^2LC\right)^2+\left(\omega_c\displaystyle\frac{L}{R}\right)^2=2\left(1-\omega_c^2LC\right)^2\\
	&1-\omega_c^2LC=\pm\omega_c\frac{L}{R}\\
	&\omega_c=\mp\frac{1}{2RC}+\sqrt{\left(\frac{1}{2RC}\right)^2+\frac{1}{LC}}
\end{align*}
$$

차단 주파수에서의 위상은 다음과 같습니다.

$$
\begin{align*}
\angle\left(-\tan^{-1}\left(\frac{\omega\displaystyle\frac{L}{R}}{1-\omega^2LC}\right)\right)&=\angle\left(\tan^{-1}\left(\mp1\right)\right)\\
	&=\mp45^{\circ}
\end{align*}
$$

공진 주파수는 다음과 같습니다.

$$
	\begin{align*}
\omega_0&=\sqrt{\omega_{c1}\omega_{c2}}\\
&=\frac{1}{\sqrt{LC}}
\end{align*}
$$

대역폭은 다음과 같습니다.

$$
	\begin{align*}
\beta&=\omega_{c2}-\omega_{c1}\\
&=\frac{1}{RC}
\end{align*}
$$

$$Q$$ 인자는 다음과 같습니다.

$$
	\begin{align*}
Q&=\frac{\omega_0}{\beta}\\
&=R\sqrt{\frac{C}{L}}
\end{align*}
$$

보드 선도를 통해 다음과 같이 나타낼 수 있습니다.

(BP)

### 일반적인 대역 차단 필터

앞서 살펴봤듯이 일반적인 2차 대역 차단 필터의 전달 함수는 다음과 같은 형태입니다.

$$
	\begin{align*}
		H(s)=\frac{s^2+\omega_0^2}{s^2+\beta s+\omega_0^2}
	\end{align*}
$$

크기와 위상은 다음과 같습니다.

$$
	\begin{align*}
	H(j\omega)&=\frac{\omega_0^2-\omega^2}{\omega_0^2-\omega^2+j\beta\omega}\\
	&=\frac{\left\vert\omega_0^2-\omega^2\right\vert}{\sqrt{\left(\omega_0^2-\omega^2\right)^2+\left(\beta\omega\right)^2}}\angle\left(-\tan^{-1}\left(\frac{\beta\omega}{\omega_0^2-\omega}\right)\right)
\end{align*}
$$

차단 주파수는 다음과 같습니다.

$$
\begin{align*}
	&\frac{1}{\sqrt{2}}=\frac{\left\vert\omega_0^2-\omega_c^2\right\vert}{\sqrt{\left(\omega_0^2-\omega_c^2\right)^2+\left(\beta\omega_c\right)^2}}\\
	&\left(\omega_0^2-\omega_c^2\right)^2+\left(\beta\omega_c\right)^2=2\left(\omega_0^2-\omega_c^2\right)^2\\
	&\omega_0^2-\omega_c^2=\pm\beta\omega_c\\
	&\omega_c=\mp\frac{\beta}{2}+\sqrt{\left(\frac{\beta}{2}\right)^2+\omega_0^2}
\end{align*}
$$

차단 주파수에서 위상은 다음과 같습니다.

$$
	\begin{align*}
	\angle\left(-\tan^{-1}\left(\frac{\beta\omega}{\omega_0^2-\omega}\right)\right)&=\angle\left(\tan^{-1}\left(\mp1\right)\right)\\
	&=\mp45^{\circ}
\end{align*}
$$

보드 선도는 다음과 같이 나타납니다.

(BP)

---

## 대역폭과 $$Q$$ 인자

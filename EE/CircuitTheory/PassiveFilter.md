# 수동 필터

---

## 개요

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

### 축전기

축전기의 임피던스는 다음과 같습니다.

$$
Z_C=\frac{1}{j\omega C}
$$

임피던스가 주파수에 반비례하는 것을 알 수 있습니다.
따라서 축전기는 저주파 신호를 막고, 고주파 신호를 흘리는 것을 알 수 있습니다.

### 인덕터

인덕터의 임피던스는 다음과 같습니다.

$$
Z_L=j\omega L
$$

임피던스가 주파수에 비례하는 것을 알 수 있습니다.
따라서 인덕터는 저주파 신호를 흘리고, 고주파 신호를 막는 것을 알 수 있습니다.

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

### RLC 병렬 회로

---

## 2차 대역 필터

### BPF 직렬 RLC 회로

### BPF 병렬 RLC 회로

---

## 2차 대역 차단 필터

### BSF 직렬 RLC 회로

### BSF 병렬 RLC 회로

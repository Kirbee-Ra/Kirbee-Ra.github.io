컨버터의 전압 모드 제어
=

---

## 목차

---

## 폐루프 컨버터

### 컨버터의 전압 피드백 회로

### 폐루프 컨버터의 블록 다이어그램

---

## 점근적 분석

이전에는 폐루프 컨버터의 전달 함수를 모두 구했습니다.
이제 **점근적 분석(Asymptotic Analysis)**을 통해 컨버터의 성능을 판단하고, 제어기의 설계 방향을 어떻게 정해야 하는지 설명하겠습니다.

### 루프 이득 설계

점근적 분석은 이름에서 알 수 있듯이 보드 선도의 점근적 근사를 통해 시스템을 분석하는 것입니다.
각 폐루프 전달 함수는 루프 이득의 크기에 따라 다음과 같이 근사할 수 있습니다.

$$
\begin{align*}
		&A_u(s)=\frac{G_{vs(s)}}{1+T_m(s)}=\begin{cases}
			\frac{G_{vs}(s)}{T_m(s)}\ \ \ \text{for }\left\vert T_m(s)\right\vert\gg1\\
			G_{vs}(s)\ \ \ \text{for }\left\vert T_m(s)\right\vert \ll1
		\end{cases}\\
		&Z_o(s)=\frac{Z_p(s)}{1+T_m(s)}=\begin{cases}
			\frac{Z_p(s)}{T_m(s)}\ \ \ \text{for }\left\vert T_m(s)\right\vert\gg1\\
			Z_p(s)\ \ \ \text{for }\left\vert T_m(s)\right\vert \ll1
		\end{cases}
	\end{align*}
$$

위 식을 보면 알 수 있듯이 루프 이득은 차단 주파수룰 중심으로 전달 함수에 미치는 영향이 달라집니다.
위 식에서 각 전달 함수의 크기를 데시벨 스케일로 나타내면 다음과 같습니다.

$$
\begin{align*}
		&20\log\left\vert A_u(j\omega)\right\vert=\begin{cases}
			20\log\left\vert G_{vs}(j\omega)\right\vert-20\log\left\vert T_m(j\omega)\right\vert\ \ \ \text{for }\left\vert T_m(j\omega)\right\vert\gg1\\
			20\log\left\vert G_{vs}(j\omega)\right\vert\ \ \ \text{for }\left\vert T_m(j\omega)\right\vert \ll1
		\end{cases}\\
		&20\log\left\vert Z_o(j\omega)\right\vert=\begin{cases}
			20\log\left\vert Z_p(j\omega)\right\vert-20\log\left\vert T_m(j\omega)\right\vert\ \ \ \text{for }\left\vert T_m(j\omega)\right\vert\gg1\\
			20\log\left\vert Z_p(j\omega)\right\vert\ \ \ \text{for }\left\vert T_m(j\omega)\right\vert \ll1
		\end{cases}
	\end{align*}
$$

이 식을 보면 루프 이득의 설계 방향을 알 수 있습니다.
모든 주파수 대역에서 각 전달 함수의 크기를 최소화하는 것이 목표임을 떠올려 봅시다.
먼저 루프 이득의 크기가 1보다 작은 경우는 설계 영역 밖입니다.
이는 고려하지 않아도 됩니다.
루프 이득의 크기가 1보다 큰 경우에 대해서 생각을 해봅시다.
개루프 전달 함수의 크기에서 루프 이득의 크기를 빼야 합니다.
각 개루프 전달 함수가 주파수 대역에 따라 어떻게 변하는지 떠올려 봅시다.

(Gvs) (Zp)

$$\left\vert G_{vs}(j\omega)\right\vert$$는 차단 주파수보다 낮은 주파수에서는 일정하고, 높은 주파수에서는 감소합니다.
즉, 고주파에서는 노이즈가 잘 감쇠된다는 것입니다.
$$\left\vert Z_p(j\omega)\right\vert$$는 영점 주파수보다 낮은 주파수에서 일정하다가, 그 이후에 증가합니다. 차단 주파수에서는 다시 감소하기 시작하여 esr 주파수에서부터 다시 일정해집니다.

이를 종합해보면, esr 주파수보다 큰 주파수를 차단 주파수로 잡고, 계속 감소하는 형태의 루프 이득을 설계해야 하는 것을 알 수 있습니다.
이제 기울기를 정해야 합니다.
기울기 $$-40\text{ dB/dec}$$ 이상으로 감쇠하는 경우는 위상이 $$-180^{\circ}$$ 이하로 떨어집니다.
이러한 설계는 루프 이득이 불안정해지므로 제외합니다.
따라서 다음과 같은 적분기만이 가능한 루프 이득의 유일한 경우입니다.

$$
T_m(s)=\frac{\omega_c}{s}
$$

이는 이상적인 루프 이득으로, 이를 바탕으로 설계된 폐루프 전달 함수들의 크기는 다음과 같이 나타납니다.

(Au) (Zo)

개루프 전달 함수와 비교하여 저주파 대역에서 많이 감쇠됐음을 알 수 있습니다.

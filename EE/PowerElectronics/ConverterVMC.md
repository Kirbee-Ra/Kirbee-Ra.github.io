컨버터의 전압 모드 제어
=

---

## 목차

---

## 컨버터의 전압 모드 제어

**전압 모드 제어(Voltage Mode Control, VMC)**는 출력 전압의 정보를 바탕으로 피드백을 하여 출력 전압을 제어하는 기법입니다.
전압 모드 제어에 활용되는 회로는 다음과 같은 형태입니다.

(VMC)

이와 같이 출력 전압이 전압 분배기에 입력됩니다.
그리고 기준 전압과 비교하여 출력된 제어 전압이 PWM 비교기에 입력됩니다.
그리고 듀티 비가 조정되어 출력 전압이 제어되는 방식입니다.
전압 모드 제어 회로를 구체적으로 어떻게 설계해야 하는지 설명하겠습니다.

---

## 점근적 분석

이전에는 폐루프 컨버터의 전달 함수를 모두 구했습니다.
앞으로 분석할 전달 함수의 기본 형태는 다음과 같습니다.

$$
F(s)=\frac{G(s)}{1+T(s)}
$$

$$G(S)$$는 개루프 전달 함수이고, $$T(s)$$는 루프 이득입니다.
이제 **점근적 분석(Asymptotic Analysis)**을 통해 컨버터의 성능을 판단하고, 제어기의 설계 방향을 어떻게 정해야 하는지 설명하겠습니다.

### 근사로 인한 오차

점근적 근사는 말 그대로 근사이기 때문에 오차가 존재합니다.
오차가 어느 정도인지 예시를 들어 알아봅시다.

### 보드 선도 그리기

주어진 전달 함수 $$F(s)$$는 루프 이득의 크기에 따라 다음과 같이 쓸 수 있습니다.

$$
F(s)=\frac{G(s)}{1+T(s)}=\begin{cases}
			\frac{G(s)}{T_m(s)}\ \ \ \text{for }\left\vert T(s)\right\vert\gg1\\
			G(s)\ \ \ \text{for }\left\vert T(s)\right\vert \ll1
		\end{cases}
$$

이를 데시벨 스케일로 나타내면 다음과 같습니다.

$$
20\log\left\vert F(j\omega)\right\vert=\begin{cases}
			20\log\left\vert G(j\omega)\right\vert-20\log\left\vert T(j\omega)\right\vert\ \ \ \text{for }\left\vert T(j\omega)\right\vert\gg1\\
			20\log\left\vert G(j\omega)\right\vert\ \ \ \text{for }\left\vert T(j\omega)\right\vert \ll1
\end{cases}
$$

먼저 $$20\log\left\vert G(j\omega)\right\vert$$와 $$20\log\left\vert T(j\omega)\right\vert$$를 그립니다.

(G, T)

다음으로 $$20\log\left\vert F(j\omega)\right\vert$$를 고주파 대역부터 그려야 합니다.
차단 주파수 이상의 대역에서는 $$20\log\left\vert T(j\omega)\right\vert$$가 $$0$$이므로 $$20\log\left\vert G(j\omega)\right\vert$$와 동일합니다.

(F G)

차단 주파수에서는 $$20\log\left\vert F(j\omega)\right\vert$$와 $$20\log\left\vert G(j\omega)\right\vert$$가 만납니다.

(F G intersect)

차단 주파수 이하의 대역에서는 $$20\log\left\vert G(j\omega)\right\vert$$에서 $$20\log\left\vert T(j\omega)\right\vert$$를 뺀 그래프를 그리면 됩니다.

(G-T)

### 전달 함수 구하기

$$G(s)$$와 $$T(s)$$만을 이용해서 보드 선도를 다 그렸습니다.
이제 $$F(s)$$를 구해야 합니다.

우선 다음과 같이 $$F(s)$$를 시간 상수 형식으로 나타냅니다.

$$
T(s)=\frac{K\prod_k\left(1+\frac{s}{\omega_{z,k}}\right)\prod_k\left(1+\frac{s}{Q_{z,k}\omega_{0z,k}}+\frac{s^2}{\omega_{0z,k}^2}\right)\cdots}{\prod_k\left(1+\frac{s}{\omega_{p,k}}\right)\prod_k\left(1+\frac{s}{Q_{p,k}\omega_{0p,k}}+\frac{s^2}{\omega_{0p,k}^2}\right)\cdots}
$$

이 식은 저주파 항부터 작성하는 것이 좋습니다.
다음으로 극점와 영점을 이전에 그려둔 보드 선도를 통해 알아냅니다.
두 점은 기울기가 변하는 지점에 위치한다는 사실을 기억합시다.
기울기가 $$\pm 1$$만큼 변하면 단일 극점이나 단일 영점이 있다는 의미입니다.
기울기가 $$\pm n$$만큼 변하면 $$n$$중 극점이나 $$n$$중 영점이 있다는 의미입니다.

(G-T)

마지막으로 계수 $$K$$를 구하면 됩니다.
$$K$$는 저주파 대역, 고주파 대역, 차단 주파수 등의 정보를 활용하여 구하면 됩니다.

---

## 점근적 분석을 통한 루프 이득 설계

점근적 분석은 이름에서 알 수 있듯이 보드 선도의 점근적 근사를 통해 시스템을 분석하는 것입니다.
각 폐루프 전달 함수는 루프 이득의 크기에 따라 다음과 같이 근사할 수 있습니다.

$$
\begin{align*}
		&A_u(s)=\frac{G_{vs}(s)}{1+T_m(s)}=\begin{cases}
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

---

## 전압 피드백 보상기 설계

루프 이득은 다음과 같습니다.

$$
T(s)=F_v(s)F_mG_{vd}(s)
$$

$$G_{vd}(s)$$는 분모가 2차식이고, 분자는 

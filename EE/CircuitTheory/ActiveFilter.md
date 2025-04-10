능동 필터
=

---

## 목차

---

## 능동 필터

**능동 필터(Active Filter)**는 능동 소자인 연산 증폭기가 이용되는 필터입니다.
수동 필터와는 다르게 신호의 증폭 또한 가능합니다.

### 활용 소자

능동 필터에는 연산 증폭기, 저항, 축전기가 이용됩니다.
인덕터는 수동 소자 중에서 가장 **비싸고**, 부피도 제일 **크며**, 가장 **무겁**습니다.
공학적 설계에 맞지 않는 요소를 모두 갖추었습니다.
따라서 필요한 상황이 아니라면 쓰지 않는 것이 좋습니다.

---

## 연산 증폭기

앞으로 활용할 연산 증폭기 회로는 다음과 같습니다.

(opamp)

연산 증폭기의 두 단자는 가상 단락되어 있으므로 반전 단자에서 KCL을 적용하면 다음과 같습니다.

$$
\begin{align*}
&\frac{0-V_{in}(s)}{Z_1(s)}+\frac{0-V_o(s)}{Z_2(s)}=0\\
&\rightarrow H(s)=\frac{V_o(s)}{V_{in}(s)}=-\frac{Z_2(s)}{Z_1(s)}
\end{align*}
$$

두 임피던스 $$Z_1,Z_2$$를 설계하여 필터를 구성하면 됩니다.
또한 이 회로를 캐스케이딩하여 구성할 수도 있습니다.

---

## 1차 저역 필터

저역 필터의 일반적인 형태는 다음과 같습니다.

$$
H(s)=\frac{A\omega_c}{s+\omega_c}
$$

축전기의 임피던스는 분모에 $$s$$가 있으므로 위 식을 $$s$$로 나눠봅시다.

---

## 1차 고역 필터

고역 필터의 일반적인 형태는 다음과 같습니다.

$$
H(s)=\frac{As}{s+\omega_c}
$$

---

## 2차 대역 필터

대역 필터는 저역 필터와 고역 필터를 캐스케이딩하여 구성할 수 있습니다.
먼저 통과 대역을 설계합니다.
다음으로 대역 필터의 차단 주파수 중에서 큰 값을 차단 주파수로 갖는 저역 필터를 설계합니다.
그리고 대역 필터의 차단 주파수 중에서 작은 값을 차단 주파수로 갖는 고역 필터를 설계합니다.
두 필터는 증폭 비 $$1$$로 설계합니다.
두 필터를 캐스케이딩합니다.
그러면 입력 신호 중에서 큰 차단 주파수보다 주파수가 작은 신호들이 저역 필터를 통과합니다.
그리고 그 중에서 작은 차단 주파수보다 주파수가 큰 신호들이 고역 필터를 통과합니다.
이러면 설계한 통과 대역에 해당하는 주파수를 가진 신호들만 통과하게 됩니다.
마지막으로 반전 증폭기를 캐스케이딩하여 증폭을 시키면 됩니다.

---

## 2차 대역 차단 필터

대역 차단 필터는 저역 필터와 고역 필터를 병렬로 연결하여 구성할 수 있습니다.
먼저 차단 대역을 설계합니다.
다음으로 대역 차단 필터의 차단 주파수 중에서 작은 값을 차단 주파수로 갖는 저역 필터를 설계합니다.
그리고 대역 차단 필터의 차단 주파수 중에서 큰 값을 차단 주파수로 갖는 고역 필터를 설계합니다.
두 필터는 증폭 비 $$1$$로 설계합니다.
그리고 두 필터의 출력에 증폭을 위한 저항을 연결합니다.
이제 두 필터를 병렬로 연결합니다.
그러면 입력 신호 중에서 작은 차단 주파수보다 주파수가 작은 신호들이 저역 필터를 통과합니다.
이 신호는 고역 필터를 통과하지 못합니다.
또한 입력 신호 중에서 큰 차단 주파수보다 주파수가 큰 신호들이 고역 필터를 통과합니다.
이 신호는 저역 필터를 통과하지 못합니다.
차단 대역의 주파수를 지닌 신호는 두 필터를 모두 통과하지 못합니다.
마지막으로 반전 증폭기를 캐스케이딩하여 증폭을 시키면 됩니다.

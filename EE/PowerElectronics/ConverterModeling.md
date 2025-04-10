# 컨버터 모델링

---

## 컨버터의 특징

컨버터는 스위칭으로 인해 시변 시스템이자, 동시에 비선형 시스템입니다.
이런 시스템은 선형 제어기를 이용하여 제어를 할 수 없습니다.
따라서 컨버터를 LTI 시스템으로 바꿔줄 필요가 있습니다.

---

## LTI 시스템 모델링 과정

컨버터는 비선형 시변 시스템입니다.
우선, 시간 의존성을 없애기 위해 스위칭 주기에 대해 평균화를 합니다.
그러면 비선형 시불변 시스템이 됩니다.
그 이후에는 특정 동작점에 대해 선형화를 합니다.
그러면 선형 시불변 시스템, 즉 LTI 시스템으로 바뀝니다.
마지막으로 주파수 영역으로 변환을 해주면 컨버터의 전달 함수를 구할 수 있습니다.

---

## [평균화 모델](./AveragedModel.md)
평균화는 그림과 같이 스위칭으로 인해 생기는 톱니 파형을 각 시각마다의 평균으로 바꾸어 매끄러운 파형으로 바꾸는 과정입니다.
평균화는 상태 공간 해석법과 회로 평균화를 통해 가능합니다.

### 온-타임 상태 공간 표현
스위치가 켜진 상태(온-타임)에서 컨버터의 상태 공간 표현식은 다음과 같습니다.

$$
		\begin{cases}
			\dot{\mathbf{x}}(t)=\mathbf{A}_{on}\mathbf{x}(t)+\mathbf{B}_{on}v_{in}(t)\\
			v_o(t)=\mathbf{C}_{on}\mathbf{x}(t)
		\end{cases}
$$

$$\mathbf{x}(t),v_{in}(t),v_o(t)$$는 각각 상태 벡터, 입력 전압, 출력 전압입니다.
$$\mathbf{A}_{on},\mathbf{B}_{on},\mathbf{C}_{on}$$는 각각 온-타임에서의 상태 행렬, 입력 행렬, 출력 행렬입니다.

### 오프-타임 상태 공간 표현

스위치가 꺼진 상태(오프-타임)에서 컨버터의 상태 공간 표현식은 다음과 같습니다.

$$
		\begin{cases}
			\dot{\mathbf{x}}(t)=\mathbf{A}_{off}\mathbf{x}(t)+\mathbf{B}_{off}v_{in}(t)\\
			v_o(t)=\mathbf{C}_{off}\mathbf{x}(t)
		\end{cases}
$$

$$\mathbf{A}_{off},\mathbf{B}_{off},\mathbf{C}_{off}$$는 각각 오프-타임에서의 상태 행렬, 입력 행렬, 출력 행렬입니다.

### 스위칭 상태 공간 표현식

다음의 스위칭 함수를 생각해봅시다.

$$
q(t)=\begin{cases}
			1\ \ \ \text{(on-time)}\\
			0\ \ \ \text{(off-time)}
		\end{cases}
$$

이를 이용해서 온-타임 표현식과 오프-타임 표현식을 하나의 식으로 나타낼 수 있습니다.
온-타임 식은 $$q(t)$$의 값을 따릅니다.
오프-타임 식은 $$1-q(t)$$의 값을 따릅니다.
따라서 다음과 같이 표현할 수 있습니다.

$$
\begin{cases}
			\dot{\mathbf{x}}(t)=\left(q(t)\mathbf{A}_{on}+\left(1-q(t)\right)\mathbf{A}_{off}\right)\mathbf{x}(t)+\left(q(t)\mathbf{B}_{on}+\left(1-q(t)\right)\mathbf{B}_{off}\right)v_{in}(t)\\
			v_o(t)=\left(q(t)\mathbf{C}_{on}+\left(1-q(t)\right)\mathbf{C}_{off}\right)\mathbf{x}(t)
		\end{cases}
$$

컨버터에서 상태 변수는 주로 인덕터 전류와 축전기 전압이 이용됩니다.
두 양은 시간 미분을 통해 각각 인덕터 전압과 축전기 전류를 표현할 수 있습니다.
시간 미분 항이 표현식에 포함돼있기 때문에 이 두 변수가 주로 이용됩니다.

### 듀티 비 함수

다음으로 스위칭 함수를 평균화해야 합니다.
이는 다음과 같이 **이동 평균(Moving Average)**을 통해 구할 수 있습니다.

$$
d(t)=\frac{1}{T_s}\int_{t-T_s}^tq(t')dt'
$$

이 식이 바로 듀티 비를 연속적으로 나타낸 함수입니다.
이 값은 그림과 같이 약간의 오차(지연)가 존재합니다.

(conti duty)

현재 시각 $$t$$에서의 듀티 비 정보를 $$T_s$$만큼의 과거로부터의 적분을 통하여 구하기 때문에 그렇습니다.
하지만 이정도 오차는 공학에서 용인되는 범위 내입니다.

### 상태 공간 표현식 평균화

다음으로 상태 공간 표현식을 평균화하면 다음과 같습니다.

$$
\begin{cases}
			\dot{\overline{\mathbf{x}}}(t)=\overline{\left(q(t)\mathbf{A}_{on}+\left(1-q(t)\right)\mathbf{A}_{off}\right)\mathbf{x}(t)+\left(q(t)\mathbf{B}_{on}+\left(1-q(t)\right)\mathbf{B}_{off}\right)v_{in}(t)}\\
			\overline{v}_o(t)=\overline{\left(q(t)\mathbf{C}_{on}+\left(1-q(t)\right)\mathbf{C}_{off}\right)\mathbf{x}(t)}
		\end{cases}
$$

우선 평균화는 적분을 통해 수행되므로 선형적인 연산입니다.
또한 각 행렬들은 모두 상수입니다.
그리고 


---

## [소신호 모델]()

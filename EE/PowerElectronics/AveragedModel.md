# 컨버터의 평균화 모델

---

## 평균화
선형 제어론을 통해 컨버터의 제어기를 설계하려면 컨버터를 LTI 시스템으로 바꿔야합니다.
그 첫번째 과정인 **평균화(Averaging)**에 대해 설명하겠습니다.
평균화는 스위칭 주기에 대해 컨버터의 동작(회로의 상태, 스위칭)의 평균을 낸다는 의미입니다.
즉, 시간 의존성을 없애고 시불변 시스템으로 바꾸는 과정입니다.
다음 파형을 살펴봅시다.

(switching sawtooth)

스위칭으로 인해 톱니 파형이 나타나는 것을 볼 수 있습니다.
매 시각마다 평균을 구하면 매끄러운 하나의 곡선으로 바뀝니다.

---

## 모델링 과정
컨버터를 살펴보면 스위치가 켜진 시간(온-타임)과 꺼진 시간(오프-타임)에서의 회로가 다릅니다.
먼저 각각의 회로에 대해 상태 공간 표현식을 구합니다.
그 후에 스위칭 함수를 통해 하나의 식으로 표현합니다.
그리고 식을 평균화하여 **스위칭 상태 공간 모델(Switched State-Space Model)**을 얻을 수 있습니다.
다음으로 **회로 평균화(Circuit Averaging)**를 해줍니다.
이 과정에서 스위치 대신 이상 변압기가 이용되고, 시간 의존성이 사라졌습니다.
이 과정을 거치면 **평균화 상태 공간 모델(Averaged State-Space Model)**을 얻을 수 있습니다.

---

## 상태 공간 평균화
먼제 온-타임과 오프-타임에서의 상태 공간 표현식을 구해야 합니다.
일반적인 상태 공간 표현식은 다음의 형태입니다.

$$
		\begin{cases}
			\dot{\mathbf{x}}(t)=\mathbf{A}\mathbf{x}(t)+\mathbf{B}v_{in}(t)\\
			v_o(t)=\mathbf{C}\mathbf{x}(t)+\mathbf{D}v_{in}(t)
		\end{cases}
$$

$$\mathbf{x}(t),v_{in}(t),v_o(t)$$는 각각 상태 벡터, 입력 전압, 출력 전압입니다.
$$\mathbf{A},\mathbf{B},\mathbf{C},\mathbf{D}$$는 각각 상태 행렬, 입력 행렬, 출력 행렬, 피드포워드 행렬입니다.
하지만 컨버터에는 입력 신호가 출력단으로 직접적으로 전달되는 경로가 없습니다. 따라서 $$\mathbf{D}$$는 $$\mathbf{0}$$입니다.
그러므로 컨버터의 상태 공간 표현식은 다음과 같습니다.

$$
		\begin{cases}
			\dot{\mathbf{x}}(t)=\mathbf{A}\mathbf{x}(t)+\mathbf{B}v_{in}(t)\\
			v_o(t)=\mathbf{C}\mathbf{x}(t)
		\end{cases}
$$

여기서 상태 변수로는 주로 인덕터 전류와 축전기 전압이 이용됩니다.
인덕터의 전압은 인덕터 전류의 시간 미분을 통해 구할 수 있고, 축전기 전류는 축전기 전압의 시간 미분을 통해 구할 수 있습니다.
두 변수의 시간 미분이 컨버터의 상태를 표현하는데 이용되므로, 두 변수가 주로 이용됩니다.

### 온-타임 상태 공간 표현식
온-타임에서 상태 공간 표현식은 다음과 같습니다.

$$
		\begin{cases}
			\dot{\mathbf{x}}(t)=\mathbf{A}_{on}\mathbf{x}(t)+\mathbf{B}_{on}v_{in}(t)\\
			v_o(t)=\mathbf{C}_{on}\mathbf{x}(t)
		\end{cases}
$$

$$on$$은 온-타임을 의미합니다.

### 오프-타임 상태 공간 표현식
오프-타임에서의 상태 공간 표현식은 다음과 같습니다.

$$
		\begin{cases}
			\dot{\mathbf{x}}(t)=\mathbf{A}_{off}\mathbf{x}(t)+\mathbf{B}_{off}v_{in}(t)\\
			v_o(t)=\mathbf{C}_{off}\mathbf{x}(t)
		\end{cases}
$$

$$off$$는 오프-타임을 의미합니다.

### 스위칭 상태 공간 모델
이제 두 식을 하나의 식으로 나타내야 합니다.
이는 다음의 스위칭 함수를 이용하면 됩니다.

$$
q(t)=\begin{cases}
			1\ \ \ \text{(on-time)}\\
			0\ \ \ \text{(off-time)}
		\end{cases}
$$

온-타임에서는 $$1$$이 출력되고, 오프-타임에서는 $$0$$이 출력됩니다. 온-타임 표현식은 스위칭 함수가 $$1$$일 때 나타나야하고 이때 오프-타임 표현식은 나타나면 안 됩니다.
따라서 온-타임 식에는 $$q(t)$$가 곱해지고, 오프-타임 식에는 $$1-q(t)$$가 곱해져야 하는 것을 알 수 있습니다.
이는 다음과 같이 나타납니다.

$$
\begin{cases}
			\dot{\mathbf{x}}(t)=\left(q(t)\mathbf{A}_{on}+\left(1-q(t)\right)\mathbf{A}_{off}\right)\mathbf{x}(t)+\left(q(t)\mathbf{B}_{on}+\left(1-q(t)\right)\mathbf{B}_{off}\right)v_{in}(t)\\
			v_o(t)=\left(q(t)\mathbf{C}_{on}+\left(1-q(t)\right)\mathbf{C}_{off}\right)\mathbf{x}(t)
		\end{cases}
$$

온-타임 식과 오프-타임 식을 하나의 식으로 나타냈습니다.

### 듀티 함수
스위칭 상태 공간 모델을 평균화하려면 우선 평균화된 스위칭 함수를 구해야 합니다.
스위칭은 듀티 비를 나타냅니다.
따라서 다음과 같이 스위칭 함수의 **이동 평균(Moving Average)**을 구하면 연속 듀티 함수를 구할 수 있습니다.

$$
d(t)=\frac{1}{T_s}\int_{t-T_s}^tq(t')dt'
$$

다음은 스위칭 함수를 듀티 함수로 바꾸는 과정을 그래프로 나타낸 것입니다.
평균화 과정에서 약간의 지연이 발생하는 것을 알 수 있습니다.
이동 평균은 적분을 통해 현재 시각에서의 듀티 비를 구하는 것입니다.
이 적분은 현재 시각에서 $$T_s$$만큼의 과거로부터 현재 시각까지 값을 누적합니다.
과거의 정보가 담겨있으므로, 지연이 발생할 수밖에 없습니다.
하지만 이 정도의 오차는 공학에서 용인됩니다.

### 평균화 상태 공간 모델

이제 스위칭 상태 공간 모델을 평균화해봅시다.

$$
\begin{cases}
			\dot{\overline{\mathbf{x}}}(t)=\overline{\left(q(t)\mathbf{A}_{on}+\left(1-q(t)\right)\mathbf{A}_{off}\right)\mathbf{x}(t)+\left(q(t)\mathbf{B}_{on}+\left(1-q(t)\right)\mathbf{B}_{off}\right)v_{in}(t)}\\
			\overline{v}_o(t)=\overline{\left(q(t)\mathbf{C}_{on}+\left(1-q(t)\right)\mathbf{C}_{off}\right)\mathbf{x}(t)}
		\end{cases}
$$

여기서 3가지의 가정을 합니다.
1. 평균화는 선형 연산입니다.
2. 행렬들은 모두 상수입니다.
3. 상태 벡터와 입력 변수가 평균으로부터의 편차가 크지 않다면, $$\overline{q(t)\mathbf{x}(t)}\approx\overline{q(t)}\overline{\mathbf{x}(t)},\overline{q(t)v_{in}(t)}\approx\overline{q(t)}\overline{v_{in}(t)}$$와 같이 근사할 수 있습니다.

이 가정을 통해 구한 평균화 상태 공간 모델은 다음과 같습니다.

$$
\begin{align*}
	&\begin{cases}
		\dot{\overline{\mathbf{x}}}(t)=\overline{\left(q(t)\mathbf{A}_{on}+\left(1-q(t)\right)\mathbf{A}_{off}\right)\mathbf{x}(t)+\left(q(t)\mathbf{B}_{on}+\left(1-q(t)\right)\mathbf{B}_{off}\right)v_{in}(t)}\\
		\overline{v}_o(t)=\overline{\left(q(t)\mathbf{C}_{on}+\left(1-q(t)\right)\mathbf{C}_{off}\right)\mathbf{x}(t)}
	\end{cases}\\
	&\rightarrow\begin{cases}
		\dot{\overline{\mathbf{x}}}(t)=\left(d(t)\mathbf{A}_{on}+\left(1-d(t)\right)\mathbf{A}_{off}\right)\overline{\mathbf{x}}(t)+\left(d(t)\mathbf{B}_{on}+\left(1-d(t)\right)\mathbf{B}_{off}\right)\overline{v}_{in}(t)\\
		\overline{v}_o(t)=\left(d(t)\mathbf{C}_{on}+\left(1-d(t)\right)\mathbf{C}_{off}\right)\overline{\mathbf{x}}(t)
	\end{cases}
		\end{align*}
$$

---

## 회로 평균화



---

## 비절연형 컨버터의 평균화 모델

각 문서 참고 바랍니다.
- [벅 컨버터]
- [부스트 컨버터]
- [벅-부스트 컨버터]

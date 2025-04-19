컨버터의 평균화 모델
=

---

## 목차
- [평균화](#평균화)
- [상태 공간 평균화](#상태-공간-평균화)
- [회로 평균화](#회로-평균화)
- [비절연형 컨버터의 평균화 모델](#비절연형-컨버터의-평균화-모델)

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

컨버터를 살펴보면 스위치가 켜진 시간(온-타임)과 꺼진 시간(오프-타임)에서의 회로가 다릅니다.
평균화를 하는 두 방법이 있습니다.
하나는 **상태 공간 평균화(State-Space Averaging)**을 이용한 것이고, 다른 하나는 **회로 평균화(Circuit Averaging)**를 이용한 것입니다.

---

## 상태 공간 평균화

우선 상태 공간 평균화에 대해 설명하겠습니다.
상태 공간 평균화는 상태 공간 모델을 이용한 평균화입니다.
온-타임과 오프-타임에서의 회로도가 다르므로 각 경우에 대해 상태 공간 표현식을 구해야 합니다.
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
두 변수의 시간 미분이 컨버터의 동 특성을 표현하는데 이용되므로, 두 변수가 주로 이용됩니다.

### 상태 공간 평균화 과정

상태 공간 평균화를 어떤 과정을 통해 하는지 설명하겠습니다.
먼저 컨버터의 온-타임과 오프-타임에서의 상태 공간 표현식을 구해야 합니다.
다음으로 스위칭 함수를 이용하여 두 식을 하나의 식으로 합쳐야 합니다.
마지막으로 평균을 내면 평균화 상태 공간 모델을 얻을 수 있습니다.

### 온-타임 상태 공간 표현식
먼저 온-타임에서 상태 공간 표현식은 다음과 같습니다.

$$
		\begin{cases}
			\dot{\mathbf{x}}(t)=\mathbf{A}_{on}\mathbf{x}(t)+\mathbf{B}_{on}v_{in}(t)\\
			v_o(t)=\mathbf{C}_{on}\mathbf{x}(t)
		\end{cases}
$$

$$on$$은 온-타임을 의미합니다.
각 컨버터에 대해 회로 법칙을 적용하여 행렬의 성분들을 모두 구하면 됩니다.

### 오프-타임 상태 공간 표현식
다음으로 오프-타임에서의 상태 공간 표현식은 다음과 같습니다.

$$
		\begin{cases}
			\dot{\mathbf{x}}(t)=\mathbf{A}_{off}\mathbf{x}(t)+\mathbf{B}_{off}v_{in}(t)\\
			v_o(t)=\mathbf{C}_{off}\mathbf{x}(t)
		\end{cases}
$$

$$off$$는 오프-타임을 의미합니다.
각 컨버터에 대해 회로 법칙을 적용하여 행렬의 성분들을 모두 구하면 됩니다.

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
식을 살펴보면 아직 스위칭 타이밍에 의존합니다.
따라서 스위칭 타이밍과 관계 없는 식을 구해야 합니다.

### 듀티 함수
스위칭 상태 공간 모델을 평균화하려면 전체 식의 평균을 구해야 합니다.
먼저 평균화된 스위칭 함수를 구해봅시다.
스위칭 함수는 듀티 비를 나타냅니다.
따라서 다음과 같이 스위칭 함수의 **이동 평균(Moving Average)**을 구하면 연속 듀티 함수를 구할 수 있습니다.

$$
d(t)=\overline{q}(t)=\frac{1}{T_s}\int_{t-T_s}^tq(t')dt'
$$

다음은 스위칭 함수를 듀티 함수로 바꾸는 과정을 그래프로 나타낸 것입니다.

먼저 실제 듀티 비는 스위칭 타이밍에 맞춰 결정되는 이산적인 양입니다.
이 이산적인 양을 연속적으로 바꿀 필요가 있습니다.
실제 듀티 비를 연속 듀티 함수와 비교해봅시다.
실제 듀티 비에 비해 약간의 지연이 발생하는 것을 알 수 있습니다.
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
3. 상태 벡터와 입력 변수가 평균으로부터의 편차가 크지 않다면, $$\overline{q(t)\mathbf{x}(t)}\approx\overline{q}(t)\overline{\mathbf{x}}(t),\overline{q(t)v_{in}(t)}\approx\overline{q}(t)\overline{v}_{in}(t)$$와 같이 근사할 수 있습니다.

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

### 평균화된 모델의 활용

우선, 이 모델을 이용하면 시간에 따라 변하지 않는 하나의 회로처럼 다룰 수 있습니다.
또한 $$\dot{x}(t)=0,v_{in}(t)=V_{in},d(t)=D$$로 두면 정상 상태를 분석할 수 있습니다.
그리고 이 모델을 이용하면 실제 스위칭 파형을 매 스위칭 주기마다 시뮬레이션하지 않아도 됩니다.
그러므로 시뮬레이션 시간이 많이 단축됩니다.
마지막으로 이 모델을 선형화하면, 주파수 영역에서 제어기를 설계할 수 있게 됩니다.

### 상태 공간 평균화의 단점

이 방법은 파워 스테이지 전체를 수식으로 표현해야 합니다.
따라서 리액턴스 성분이 많은 컨버터일수록 시간이 오래 걸립니다.
또 다른 문제는 상태 표현식의 형태입니다.
이런 형태의 표현식은 일반적인 시뮬레이션 프로그램에 직접적으로 적용할 수 없습니다.

---

## 회로 평균화

다음으로 **회로 평균화(Circuit Averaging)**에 대해 설명하겠습니다.
다음 과정을 통해 이루어집니다.

1. 파워 스테이지의 각 소자와 관련된 변수들의 동작에 대한 평균 식을 구합니다.
2. 1번을 만족하도록 각 소자를 등가 회로로 치환합니다.
3. 이렇게 얻어진 등가 회로를 파워 스테이지의 각 소자들에 적용합니다.
4. 이 과정을 파워 스테이지 내의 모든 소자들에 대해 적용합니다.

각 소자들 일일이 하나씩 모델링할 필요는 없습니다.
몇몇 소자가 그룹화되어 하나의 소자처럼 동작한다면, 그 그룹 전체를 등가 회로로 모델링하면 됩니다.

### PWM 스위치

먼저 스위치를 평균화 해봅시다.
컨버터는 기본적으로 SPDT 스위치의 스위칭을 통해 동작합니다.
이러한 PWM 방식의 컨버터에서 쓰이는 스위치를 **PWM 스위치(PWM Switch)**라고 합니다.
다음의 PWM 스위치를 살펴봅시다.

(PWM Switch)

$$a$$(active)단자, $$p$$(passive)단자, $$c$$(common)단자로 총 3개의 단자로 구성된 스위치입니다.
$$a$$단자에는 직접 신호를 입력하여 구동시키는 스위치가 연결됩니다.
보통 트랜지스터를 이용합니다.
$$p$$단자에는 주변 환경에 따라 간접적으로 구동되는 스위치가 연결됩니다.
보통 다이오드를 이용합니다.
$$c$$단자는 각 단자에 대해 도통될 수 있는 경로를 제공합니다.

온-타임에는 $$a-c$$경로가 도통되고, 오프-타임에는 $$c-p$$경로가 도통됩니다.
비절연형 컨버터에서는 $$a$$단자에 MOSFET이 연결되어 있고, $$p$$단자에는 다이오드가 연결되어 있으며, $$c$$단자에는 인덕터가 연결되어 있습니다.
이 PWM 스위치를 다음과 같이 SPDT 스위치로 모델링해봅시다.

(spdt)

우리가 주목할 변수는 $$v_{ap},v_{cp},i_a,i_c$$입니다.
그리고 $$d$$는 온-타임(듀티 비)을 나타냅니다.
$$a$$단자에 흐르는 전류는 $$a-c$$경로가 단락될 때만 흐릅니다.
또한 $$c-p$$단자 사이의 전압은 $$a-c$$경로가 단락될 때만 걸립니다.
이런 전압과 전류의 관계를 스위칭 함수를 이용하면 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
			v_{cp}(t)=v_{ap}(t)q(t)\\
			i_a(t)=i_c(t)q(t)
		\end{cases}
$$

좌변의 변수들은 연속적이지 않습니다.
연속된 변수로 만들기 위해 이전에 언급한 가정을 가지고 평균화하면 다음과 같습니다.

$$
\begin{cases}
			\overline{v}_{cp}(t)=\overline{v_{ap}(t)q(t)}\approx\overline{v}_{ap}(t)d(t)\\
			\overline{i}_{a}(t)=\overline{i_{c}(t)q(t)}\approx\overline{i}_{c}(t)d(t)
		\end{cases}
$$

PWM 스위치는 손실이 없는 소자입니다.
다음과 같이 전력이 전달된다고 생각할 수 있습니다.

$$
	\begin{align*}
&\overline{v}_{ap}\overline{i}_ad(t)=\overline{v}_{cp}d(t)\overline{i}_c\\
&\rightarrow\overline{v}_{ap}\overline{i}_a=\overline{v}_{cp}\overline{i}_c
	\end{align*}
$$

위 관계식과 전력 전달 식을 살펴보면 PWM 스위치의 평균화 모델이 턴 비가 $$1:d(t)$$인 이상 변압기의 관계식과 같음을 알 수 있습니다.
또한 PWM 스위치는 단자가 3개인 소자입니다.
따라서 다음과 같은 이상 변압기로 모델링할 수 있습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/평균화 스위치.png" alt="PWM 스위치의 평균화 모델" width="80%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. PWM 스위치의 평균화 모델)
  </figcaption>
</figure>

### 평균화된 파형

다음의 파형을 살펴봅시다.

(waveform)

왼쪽 파형을 평균화하면 오른쪽 파형이 도출됩니다.
이와 같이 평균화를 통해 스위칭에 의한 효과가 사라집니다.

### 회로 평균화의 의의

평균화 모델은 정상 상태 분석을 위해 활용되기도 합니다.
정상 상태에서는 연속 듀티 함수가 정상 상태 듀티 비 $$D$$로 바뀝니다.
또한 인덕터는 단락된 상태이고, 축전기는 개방된 상태입니다.
이 조건 하에 특정 동작점에서 회로 법칙을 통해 출력 전압을 구할 수 있습니다.

---

## 비절연형 컨버터의 평균화 모델

자세한 내용은 각 문서 참고 바랍니다.
- [벅 컨버터]
- [부스트 컨버터]
- [벅-부스트 컨버터]

### 벅 컨버터

벅 컨버터의 평균화 모델은 다음과 같습니다.

### 부스트 컨버터

부스트 컨버터의 평균화 모델은 다음과 같습니다.

### 벅-부스트 컨버터

벅-부스트 컨버터의 평균화 모델은 다음과 같습니다.

---

## 같이 보기
- [컨버터 모델링](./ConverterModeling.md)
- [컨버터의 소신호 모델](./ConverterSmallSignalModel.md)
- [컨버터의 전달 함수](./ConverterTransferFunction.md)

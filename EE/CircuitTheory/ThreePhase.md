3상 시스템
=

---

## 목차

---

## 단상 시스템

흔히 다루는 전원이 한 개인 시스템을 **단상 시스템(Single Phase System)**이라고 합니다.

$$
v(t)=V_m\cos\left(\omega t\right)
$$

다음 그림과 같이 단상 시스템은 전원과 부하, 그리고 두 개의 도선으로 구성됩니다.

(single ph)

도선 중 하나는 부하로 전류를 흘리고, 또 하나는 전류가 다시 전원으로 되돌아오게 합니다.
즉, 전류가 나가는 경로와 들어오는 경로의 총 두 전선이 필요합니다.

---

## 3상 시스템

**3상 시스템(Three Phase System)**은 다음 그림과 같이 전원이 3개인 시스템입니다.
각각의 위상을 갖고 있습니다.

각 상을 $$a$$상, $$b$$상, $$c$$상이라고 부릅니다.

발전소에서는 3상의 전력을 생산하고, 송전합니다.
그리고 가정에서는 그 중 한 개 또는 두 개의 상으로부터 전선을 따와서 부하에 연결합니다.

### 3상 시스템 구축

3상 시스템을 어떻게 구축하는지 설명하겠습니다.
앞서 단상의 경우와 같이 간단한 전력 전달 회로를 생각해봅시다.

(simple)

동일한 회로를 통해 $$3$$배의 전력을 전송할 수 있을 지는 알 수 없습니다. 
전선은 모두 허용 전류 규격이 존재합니다.
전류의 열작용에 의해 발열이 생기고, 정격 값을 초과하면 화재의 위험성이 있습니다.
주어진 회로에 정격 값만큼의 전류가 흐른다고 해봅시다.
그렇 다면 $$3$$배의 전력을 전송하기 위해서는 전선의 단면적이 최소 $$3$$배는 되어야 합니다.
더 굵은 도선을 사용하는 대신에 전선의 양을 $$3$$배로 늘려봅시다.

(6 wires)

전류가 나가는 경로 3개와 다시 들어오는 경로 3개가 존재합니다.
단상 회로 3개가 병렬로 연결된 회로라고 볼 수 있습니다.
단상 회로 3개로 나눠서 생각해봅시다.

(single)

여기서 두 회로는 전원의 위상을 바꾸어도 동일한 전력을 전달합니다.
따라서 전원의 위상을 바꿔도 문제가 없습니다.

(ph shift)

여기서 가정을 해봅시다.
세 전원의 진폭이 같고, 위상만 $$120^{\circ}$$만큼씩 차이가 난다고 해봅시다.
부하는 모두 같은 상황입니다.
그러므로 각각의 전류는 진폭이 같고 위상만 $$120^{\circ}$$만큼씩 차이가 나게 됩니다.
이런 경우, 세 전류의 합은 항상 $$0$$입니다.
이 사실을 이용할 수 있습니다.
우선 전류가 나가는 경로는 전력 전달을 위한 경로로, 그냥 둡시다.
그리고 돌아오는 경로를 하나의 전선으로 합쳐봅시다.

(4 wires)

분명 $$3$$배의 단면적을 갖는 전선이 필요하지만, 이 전선에 흐르는 전류는 세 전류의 합으로 나타낼 수 있고, 그 값은 항상 $$0$$입니다.
즉, 이 전선에는 전류가 흐르지 않는 상태로, 개방 회로와 동등한 효과를 냅니다.
그러므로 이 전선을 없어도 됩니다.

(3 wires)

앞서 언급한 가정 하에 $$3$$개의 전선으로만 구성된 시스템이 구축되었습니다.
이는 특수한 경우로, 세 전원의 진폭이 같고, 위상만 $$120^{\circ}$$만큼씩 차이가 나며, 부하는 모두 동일합니다.
이를 **평형 3상 시스템(Balanced Three Phase System)**이라고 합니다.

### 상전압과 선간 전압

**상전압(Phase Voltage)**은 각 전원 양단의 전압을 의미합니다. 각 상에 대한 전압이므로 상전압이라고 합니다.
**선간 전압(Line to Line Voltage)**은 두 전선 사이의 전압을 의미합니다.
두 양은 전원의 결선 방법에 따라 관계가 달라집니다.

### 상전류와 선전류

**상전류(Phase Current)**는 각 전원에 흐르는 전류를 의미합니다. 각 상에 대한 전류이므로 상전류라고 합니다.
**선전류(Line Current)**는 전선에 흐르는 의미합니다.
두 양은 전원의 결선 방법에 따라 관계가 달라집니다.

---

## 평형 3상 시스템

전원의 진폭과 주파수가 같고, 위상이 각각 $$120^{\circ}$$씩 차이나며, 부하 또한 모두 같은 3상 시스템을 **평형 3상 시스템(Balanced Three Phase System)**이라고 합니다.

### 순시 전력

다음과 같은 전압으로 전력을 송전한다고 해봅시다.

$$
\begin{cases}
		v_a(t)=V_m\cos\left(\omega t\right)\\
	v_b(t)=V_m\cos\left(\omega t-120^{\circ}\right)\\
	v_c(t)=V_m\cos\left(\omega t+120^{\circ}\right)
\end{cases}
$$

평형 3상 시스템이므로 송전 전류를 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
		i_a(t)=I_m\cos\left(\omega t-\phi\right)\\
	i_b(t)=I_m\cos\left(\omega t-\phi-120^{\circ}\right)\\
	i_c(t)=I_m\cos\left(\omega t-\phi+120^{\circ}\right)
\end{cases}
$$

$$a$$상의 순시 전력은 다음과 같습니다.

$$
p_a(t)=\frac{V_mI_m}{2}\cos\phi+\frac{V_mI_m}{2}\cos\left(2\omega t+\phi\right)
$$

다른 두 상의 순시 전력은 다음과 같이 위상만 이동시켜 나타낼 수 있습니다.

$$
	\begin{align*}
&p_b(t)=\frac{V_mI_m}{2}\cos\phi+\frac{V_mI_m}{2}\cos\left(2\omega t-\phi-120^{\circ}\right)\\
&p_c(t)=\frac{V_mI_m}{2}\cos\phi+\frac{V_mI_m}{2}\cos\left(2\omega t-\phi+120^{\circ}\right)
\end{align*}
$$

세 전력을 더하면 다음과 같습니다.

$$
p_{total}(t)=\frac{3V_mI_m}{2}\cos\phi
$$

$$120^{\circ}$$씩 차이 나는 항들은 더하면 모두 $$0$$이므로 이와 같이 나타납니다.
이는 시간에 의존하지 않는 상수로, 평형 3상 시스템에서의 순시 전력은 항상 일정한 것을 알 수 있습니다.

### 위상자 다이어그램

평형 3상 시스템의 위상자 다이어그램은 다음과 같이 나타낼 수 있습니다.

---

## 3상 시스템의 발전기

3상 시스템은 기본적으로 사인파 교류 형태의 전원을 갖고 있습니다.
먼저 교류 발전기의 기본 원리를 짚고 넘어갑시다.

### 단상 교류 발전기

단상 교류는 흔히 아는 전자기 유도를 통해 얻을 수 있습니다.
실제로 쓰이는 형태의 발전기를 간단하게 나타낸 그림을 통해 설명하겠습니다.

(single gen)

그림과 같은 형태의 기기를 생각해봅시다.
그림을 보시면 가운데에 자석이 있고, 권선이 어딘가에 감겨져 있는 것을 볼 수 있습니다.
권선이 감겨진 장치는 **고정자(Stator)**라고 하며, 고정되어 움직이지 않는 부분입니다.
그리고 자속을 변화시키기 위해 자석을 회전시키는 장치가 자석에 붙어있습니다.
이를 **회전자(Rotor)**라고 합니다.
그림을 보시면 권선을 감을 수 있는 부분이 세 곳입니다.
이는 3상 교류 발전기의 기본적인 형태입니다.
3상을 다 분석하기 전에 먼저 $$a$$상에 대해서만 봅시다.

(a ph)

위 그림은 $$a$$상에 대해서만 나타낸 발전기입니다.
자석이 회전을 하면, $$a$$상의 권선의 단면을 통과하는 쇄교 자속을 다음과 같이 나타낼 수 있습니다.

$$
\Lambda_a(t)=\Lambda_0\cos\theta
$$

자석을 일정한 각속도 $$\omega$$로 회전시키면 다음과 같이 나타낼 수 있습니다.

$$
\Lambda_a(t)=\Lambda_0\cos\left(\omega t+\phi\right)
$$

패러데이 법칙에 따라 유도 기전력은 다음과 같습니다.

$$
	\begin{align*}
v_a(t)&=-\dot{\Lambda}_a\\
&=\omega\Lambda_0\sin\left(\omega t+\phi\right)\\
&=V_{ph}\sin\left(\omega t+\phi\right)
\end{align*}
$$

이 유도 기전력이 바로 $$a$$상의 상전압입니다.

### 3상 교류 발전기
이제 $$b$$상과 $$c$$상까지 고려해봅시다.
두 상은 $$a$$상과 위상이 다르므로 그림과 같이 $$120^{\circ}$$씩 간격을 두어 배치합니다.

(3 ph gen)

이와 같이 물리적으로 $$120^{\circ}$$씩 간격을 두어 배치를 하면, 쇄교 자속이 각 권선을 통과하는 각이 달라지므로 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
	\Lambda_a(t)=\Lambda_0\cos\theta\\
	\Lambda_b(t)=\Lambda_0\cos\left(\theta-120^{\circ}\right)\\
	\Lambda_c(t)=\Lambda_0\cos\left(\theta+120^{\circ}\right)
\end{cases}
$$

자석을 일정한 각속도 $$\omega$$로 회전시키면 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
	\Lambda_a(t)=\Lambda_0\cos\left(\omega t+\phi\right)\\
	\Lambda_b(t)=\Lambda_0\cos\left(\omega t+\phi-120^{\circ}\right)\\
	\Lambda_c(t)=\Lambda_0\cos\left(\omega t+\phi+120^{\circ}\right)
\end{cases}
$$

각 상의 상전압은 다음과 같습니다.

$$
\begin{cases}
	v_{an}(t)=-\dot{\Lambda}_a=\omega\Lambda_0\cos\left(\omega t+\phi\right)=V_{ph}\cos\left(\omega t+\phi\right)\\
	v_{bn}(t)=-\dot{\Lambda}_b=\omega\Lambda_0\cos\left(\omega t+\phi-120^{\circ}\right)=V_{ph}\cos\left(\omega t+\phi-120^{\circ}\right)\\
	v_{cn}(t)=-\dot{\Lambda}_c=\omega\Lambda_0\cos\left(\omega t+\phi+120^{\circ}\right)=V_{ph}\cos\left(\omega t+\phi+120^{\circ}\right)
\end{cases}
$$

그리고 각 권선의 단자의 결선법은 두 가지가 있습니다.

---

## 3상 전원의 Y 결선


다음 그림과 같이 각 전원들이 Y 결선 되었다고 해봅시다.

(Y)

이때 선간 전압은 KVL에 의해 다음과 같이 구할 수 있습니다.

$$
\begin{cases}
	-\mathbf{V}_{an}+\mathbf{V}_{ab}+\mathbf{V}_{bn}=0&\rightarrow\mathbf{V}_{ab}=\mathbf{V}_{an}-\mathbf{V}_{bn}\\
	-\mathbf{V}_{bn}+\mathbf{V}_{bc}+\mathbf{V}_{cn}=0&\rightarrow\mathbf{V}_{bc}=\mathbf{V}_{bn}-\mathbf{V}_{cn}\\
	-\mathbf{V}_{cn}+\mathbf{V}_{ca}+\mathbf{V}_{bn}=0&\rightarrow\mathbf{V}_{ca}=\mathbf{V}_{cn}-\mathbf{V}_{an}
\end{cases}
$$

평형 3상 시스템에 대해 생각해봅시다. 각 상전압을 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
			\mathbf{V}_{an}=V_{ph}\angle\phi\\
			\mathbf{V}_{bn}=V_{ph}\angle\left(\phi-120^{\circ}\right)\\
			\mathbf{V}_{cn}=V_{ph}\angle\left(\phi+120^{\circ}\right)
		\end{cases}
$$

각 선간 전압은 다음과 같습니다.

$$
\begin{cases}
	\mathbf{V}_{ab}=\mathbf{V}_{an}-\mathbf{V}_{bn}=\sqrt{3}V_{ph}\angle\left(\phi+30^{\circ}\right)\\
	\mathbf{V}_{bc}=\mathbf{V}_{bn}-\mathbf{V}_{cn}=\sqrt{3}V_{ph}\angle\left(\phi-90^{\circ}\right)\\
	\mathbf{V}_{ca}=\mathbf{V}_{cn}-\mathbf{V}_{an}=\sqrt{3}V_{ph}\angle\left(\phi+150^{\circ}\right)
\end{cases}
$$

상전압에 비해 진폭이 $$\sqrt{3}$$배가 되었고, 위상은 $$+30^{\circ}$$만큼 이동했습니다.

이제 전류에 대해 생각해봅시다.
각 전선에 한 전원씩 연결되어 있습니다.
따라서 전원을 Y 결선하는 경우는 상전류와 선전류가 동일합니다.

---

## 3상 전원의 Δ 결선

다음 그림과 같이 각 전원들이 Δ 결선 되었다고 해봅시다.

(delta)




---

## 부하의 Y 결선과 Δ 결선

---

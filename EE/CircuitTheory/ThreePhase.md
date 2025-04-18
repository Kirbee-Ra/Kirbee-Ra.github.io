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
그러므로 이 전선은 없어도 됩니다.

(3 wires)

앞서 언급한 가정 하에 $$3$$개의 전선으로만 구성된 시스템이 구축되었습니다.
이는 특수한 경우로, 세 전원의 진폭이 같고, 위상만 $$120^{\circ}$$만큼씩 차이가 나며, 부하는 모두 동일합니다.
이를 **평형 3상 시스템(Balanced Three Phase System)**이라고 합니다.
이 내용은 [뒤](#y-delta-connection)에서 자세히 다루겠습니다.

### 상전압과 선간 전압

**상전압(Phase Voltage)**은 각 전원 양단의 전압을 의미합니다. 각 상에 대한 전압이므로 상전압이라고 합니다.
**선간 전압(Line to Line Voltage)**은 두 전선 사이의 전압을 의미합니다.
두 양은 전원의 결선 방법에 따라 관계가 달라집니다.

### 상전류와 선전류

**상전류(Phase Current)**는 각 전원에 흐르는 전류를 의미합니다. 각 상에 대한 전류이므로 상전류라고 합니다.
**선전류(Line Current)**는 전선에 흐르는 전류를 의미합니다.
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
p_{total}(t)=\frac{3}{2}V_mI_m\cos\phi
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
&=V_m\sin\left(\omega t+\phi\right)
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
	v_{an}(t)=-\dot{\Lambda}_a=\omega\Lambda_0\cos\left(\omega t+\phi\right)=V_m\cos\left(\omega t+\phi\right)\\
	v_{bn}(t)=-\dot{\Lambda}_b=\omega\Lambda_0\cos\left(\omega t+\phi-120^{\circ}\right)=V_m\cos\left(\omega t+\phi-120^{\circ}\right)\\
	v_{cn}(t)=-\dot{\Lambda}_c=\omega\Lambda_0\cos\left(\omega t+\phi+120^{\circ}\right)=V_m\cos\left(\omega t+\phi+120^{\circ}\right)
\end{cases}
$$

그리고 각 권선의 단자의 결선법은 두 가지가 있습니다.

---

## 3상 전원의 Y 결선

다음과 같이 권선에서 고정자를 향해 전류가 들어가는 부분만 전선에 연결하고, 전류가 나가는 부분을 서로 단락시켜 봅시다.

(Y)

이를 회로도로 나타내면 다음과 같습니다.

(Y sch)

이와 같이 세 전원의 전위가 낮은 부분끼리 단락시키고, 전위가 높은 부분을 전선에 연결하는 결선법을 **Y 결선(Y/Wye Connection)**이라고 합니다.
또는 **T 결선(T/Tee Connection)**이라고 합니다.
결선의 형태와 비슷한 문자로 표현한 것입니다.
Y 결선은 그림과 같이 세 전선과 하나의 중성선으로 구성됩니다.
이때 선간 전압은 KVL에 의해 다음과 같이 구할 수 있습니다.

$$
\begin{cases}
	-\mathbf{V}_{an}+\mathbf{V}_{ab}+\mathbf{V}_{bn}=0&\rightarrow\mathbf{V}_{ab}=\mathbf{V}_{an}-\mathbf{V}_{bn}\\
	-\mathbf{V}_{bn}+\mathbf{V}_{bc}+\mathbf{V}_{cn}=0&\rightarrow\mathbf{V}_{bc}=\mathbf{V}_{bn}-\mathbf{V}_{cn}\\
	-\mathbf{V}_{cn}+\mathbf{V}_{ca}+\mathbf{V}_{bn}=0&\rightarrow\mathbf{V}_{ca}=\mathbf{V}_{cn}-\mathbf{V}_{an}
\end{cases}
$$

평형 3상 시스템에 대해 생각해봅시다.
각 상전압을 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
			\mathbf{V}_{an}=V_m\angle\phi\\
			\mathbf{V}_{bn}=V_m\angle\left(\phi-120^{\circ}\right)\\
			\mathbf{V}_{cn}=V_m\angle\left(\phi+120^{\circ}\right)
		\end{cases}
$$

각 선간 전압은 다음과 같습니다.

$$
\begin{cases}
	\mathbf{V}_{ab}=\mathbf{V}_{an}-\mathbf{V}_{bn}=\sqrt{3}V_m\angle\left(\phi+30^{\circ}\right)\\
	\mathbf{V}_{bc}=\mathbf{V}_{bn}-\mathbf{V}_{cn}=\sqrt{3}V_m\angle\left(\phi-90^{\circ}\right)\\
	\mathbf{V}_{ca}=\mathbf{V}_{cn}-\mathbf{V}_{an}=\sqrt{3}V_m\angle\left(\phi+150^{\circ}\right)
\end{cases}
$$

상전압에 비해 진폭이 $$\sqrt{3}$$배가 되었고, 위상은 $$+30^{\circ}$$만큼 이동했습니다.

이제 전류에 대해 생각해봅시다.
각 전선에 한 전원씩 연결되어 있습니다.
따라서 전원을 Y 결선하는 경우는 상전류와 선전류가 동일합니다.

---

## 3상 전원의 Δ 결선

다음과 같이 한 상에서 전위가 낮은 부분이 다른 상의 전위가 높은 부분에 단락된 경우를 살펴봅시다.

(delta)

이를 회로도로 나타내면 다음과 같습니다.

이와 같은 결선법을 **Δ 결선(Δ/Delta Connection)**이라고 합니다.
또는 **π 결선(π/Pi Connection)**이라고도 합니다.
회로를 보시면 아시겠지만, 이런 경우는 상전압과 선간 전압이 동일합니다.
각 전원의 양단이 두 전선에 각각 연결되어 있기 때문입니다.

하지만 상전류와 선전류는 다릅니다.
각 마디에 KCL을 적용하면 다음과 같습니다.

$$
\begin{cases}
	-\mathbf{I}_{ab}+\mathbf{I}_a+\mathbf{I}_{ca}=0&\rightarrow\mathbf{I}_a=\mathbf{I}_{ab}-\mathbf{I}_{ca}\\
	-\mathbf{I}_{bc}+\mathbf{I}_b+\mathbf{I}_{ab}=0&\rightarrow\mathbf{I}_b=\mathbf{I}_{bc}-\mathbf{I}_{ab}\\
	-\mathbf{I}_{ca}+\mathbf{I}_c+\mathbf{I}_{bc}=0&\rightarrow\mathbf{I}_c=\mathbf{I}_{ca}-\mathbf{I}_{bc}
\end{cases}
$$

평형 3상 시스템에 대해 생각해봅시다.
각 상전류를 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
	\mathbf{I}_{ab}=I_m\angle\phi\\
	\mathbf{I}_{bc}=I_m\angle\left(\phi-120^{\circ}\right)\\
	\mathbf{I}_{ca}=I_m\angle\left(\phi+120^{\circ}\right)
\end{cases}
$$

각 선전류는 다음과 같습니다.

$$
\begin{cases}
	\mathbf{I}_a=\mathbf{I}_{ab}-\mathbf{I}_{ca}=\sqrt{3}I_m\angle\left(\phi+30^{\circ}\right)\\
	\mathbf{I}_b=\mathbf{I}_{bc}-\mathbf{I}_{ab}=\sqrt{3}I_m\angle\left(\phi-90^{\circ}\right)\\
	\mathbf{I}_c=\mathbf{I}_{ca}-\mathbf{I}_{bc}=\sqrt{3}I_m\angle\left(\phi+150^{\circ}\right)
\end{cases}
$$

상전류에 비해 진폭이 $$\sqrt{3}$$배가 되었고, 위상은 $$+30^{\circ}$$만큼 이동했습니다.

---

<h2 id="y-delta-connection">부하의 Y 결선과 Δ 결선</h2>

3상 시스템에는 부하가 총 3개가 연결됩니다.
부하 또한 전원과 마찬가지로 Y 결선과 Δ 결선이 있습니다.
두 경우 모두 부하 양단에 걸린 전압을 알면 부하 전류를 구할 수 있습니다.

### Y 결선 전원 - Y 결선 부하

전원과 부하가 모두 Y 결선된 상황을 살펴봅시다.

(YY)

이 경우는 부하 양단에 걸린 전압이 상전압과 동일합니다.
따라서 다음과 같이 상전압을 부하 임피던스로 나누면 부하 전류를 구할 수 있습니다.

$$
\mathbf{I}_L=\frac{\mathbf{V}_{ph}}{Z}
$$

이제 평형 3상 시스템에 대해 생각해봅시다.

상전압은 다음과 같습니다.

$$
		\begin{cases}
			\mathbf{V}_{an}=V_m\angle\phi\\
			\mathbf{V}_{bn}=V_m\angle\left(\phi-120^{\circ}\right)\\
			\mathbf{V}_{cn}=V_m\angle\left(\phi+120^{\circ}\right)
		\end{cases}
$$

부하를 다음과 같다고 해봅시다.

$$
Z=Z_m\angle\theta
$$

각 부하에 흐르는 전류는 다음과 같습니다.

$$
\begin{cases}
	\mathbf{I}_{L,a}=\displaystyle\frac{\mathbf{V}_{an}}{Z}=\displaystyle\frac{V_m}{Z_m}\angle\left(\phi-\theta\right)\\
	\mathbf{I}_{L,b}=\displaystyle\frac{\mathbf{V}_{bn}}{Z}=\displaystyle\frac{V_m}{Z_m}\angle\left(\phi-120^{\circ}-\theta\right)\\
	\mathbf{I}_{L,c}=\displaystyle\frac{\mathbf{V}_{cn}}{Z}=\displaystyle\frac{V_m}{Z_m}\angle\left(\phi+120^{\circ}-\theta\right)
\end{cases}
$$

전류들의 위상이 $$120^{\circ}$$씩 차이가 납니다.

중성선에서 KCL을 적용해보면 다음과 같습니다.

$$
	\begin{align*}
&\mathbf{I}_{nN}-\mathbf{I}_{L,a}-\mathbf{I}_{L,b}-\mathbf{I}_{L,c}=0\\
&\rightarrow\mathbf{I}_{nN}=\mathbf{I}_{L,a}+\mathbf{I}_{L,b}+\mathbf{I}_{L,c}
\end{align*}
$$

우변은 진폭이 같고 위상이 $$120^{\circ}$$씩 차이가 나기 때문에 $$\mathbf{0}$$이 됩니다.
따라서 중성선에는 전류가 흐르지 않습니다.
이런 경우는 중성선이 없어도 됩니다.
따라서 다음과 같이 전선을 3개만 쓰는 **3상 3선식 시스템(Three-Phase Three-Wires System, 3P3W System)**으로 구성할 수 있습니다.

### Δ 결선 전원 - Δ 결선 부하

다음으로 전원과 부하 모두 Δ 결선된 회로를 살펴봅시다.

(delta delta)

이 경우는 부하 양단에 걸린 전압이 선간 전압과 동일합니다.
또한 각 전원의 상전압과 동일합니다.
그러므로 부하 전류는 다음과 같이 상전압을 부하 임피던스로 나누면 구할 수 있습니다.

$$
\mathbf{I}_L=\frac{\mathbf{V}_{ph}}{Z}
$$

상전압이 다음과 같다고 해봅시다.

$$
\begin{cases}
	\mathbf{V}_{ab}=V_m\angle\phi\\
	\mathbf{V}_{bc}=V_m\angle\left(\phi-120^{\circ}\right)\\
	\mathbf{V}_{ca}=V_m\angle\left(\phi+120^{\circ}\right)
\end{cases}
$$

각 부하에 흐르는 전류는 다음과 같습니다.

$$
\begin{cases}
	\mathbf{I}_{L,ab}=\displaystyle\frac{\mathbf{V}_{ab}}{Z}=\displaystyle\frac{V_m}{Z_m}\angle\left(\phi-\theta\right)\\
	\mathbf{I}_{L,bc}=\displaystyle\frac{\mathbf{V}_{bc}}{Z}=\displaystyle\frac{V_m}{Z_m}\angle\left(\phi-120^{\circ}-\theta\right)\\
	\mathbf{I}_{L,ca}=\displaystyle\frac{\mathbf{V}_{ca}}{Z}=\displaystyle\frac{V_m}{Z_m}\angle\left(\phi+120^{\circ}-\theta\right)
\end{cases}
$$

부하 전류들을 이용해 선전류를 구할 수 있습니다.
각 마디에 KCL을 적용하면 다음과 같습니다.

$$
\begin{cases}
	\mathbf{I}_a=\mathbf{I}_{L,ab}-\mathbf{I}_{L,ca}=\displaystyle\frac{\sqrt{3}V_m}{Z_m}\angle\left(\phi-30^{\circ}-\theta\right)\\
	\mathbf{I}_b=\mathbf{I}_{L,bc}-\mathbf{I}_{L,ab}=\displaystyle\frac{\sqrt{3}_m}{Z_m}\angle\left(\phi-150^{\circ}-\theta\right)\\
	\mathbf{I}_c=\mathbf{I}_{L,ca}-\mathbf{I}_{L,bc}=\displaystyle\frac{\sqrt{3}V_m}{Z_m}\angle\left(\phi+90^{\circ}-\theta\right)
\end{cases}
$$

### 부하의 Y-Δ 변환

이전에 언급한 경우들은 모두 전원과 부하가 동일한 방법으로 결선된 것들이었습니다.
결선법이 다른 경우는 전원의 결선법에 맞추어 부하의 결선법을 변환하는 것이 좋습니다.
다음 그림을 살펴봅시다.

(Y Δ load)

두 결선법 사이의 관계식을 알아내기 위해 우선 $$A$$ 단자와 $$B$$ 단자 사이의 등가 임피던스를 구해봅시다.
Y 결선의 경우를 먼저 살펴봅시다.
$$C$$ 단자는 개방 상태이므로 임피던스 $$Z_C$$는 무시할 수 있습니다.
따라서 등가 임피던스는 다음과 같습니다.

$$
Z_{eq}=Z_A+Z_B
$$

다음으로 Δ 결선된 경우를 살펴봅시다.
이 경우는 $$Z_1$$과 $$Z_2$$가 직렬로 연결되어 있고, 이 직렬 연결된 임피던스가 $$Z_3$$와 병렬로 연결되어 있습니다.
따라서 등가 임피던스는 다음과 같습니다.

$$
Z_{eq}=Z_3\vert\vert\left(Z_1+Z_2\right)
$$

두 양은 같으므로 다음과 같습니다.

$$
Z_A+Z_B=Z_3\vert\vert\left(Z_1+Z_2\right)
$$

다른 단자들에 대해서도 이 방법을 적용하면 아래와 같은 관계식 3개를 유도할 수 있습니다.

$$
		\begin{cases}
Z_A+Z_B=Z_3\vert\vert\left(Z_1+Z_2\right)\\
Z_B+Z_C=Z_1\vert\vert\left(Z_2+Z_3\right)\\
Z_C+Z_A=Z_2\vert\vert\left(Z_3+Z_1\right)
\end{cases}
$$

먼저 Y$$\rightarrow$$Δ 변환식은 다음과 같습니다.

$$
		\begin{cases}
Z_1=\displaystyle\frac{Z_AZ_B+Z_BZ_C+Z_CZ_A}{Z_A}\\
Z_2=\displaystyle\frac{Z_AZ_B+Z_BZ_C+Z_CZ_A}{Z_B}\\
Z_3=\displaystyle\frac{Z_AZ_B+Z_BZ_C+Z_CZ_A}{Z_C}
\end{cases}
$$

Δ$$\rightarrow$$Y 변환식은 다음과 같습니다.

$$
		\begin{cases}
Z_A=\displaystyle\frac{Z_2Z_3}{Z_1+Z_2+Z_3}\\
Z_B=\displaystyle\frac{Z_3Z_1}{Z_1+Z_2+Z_3}\\
Z_C=\displaystyle\frac{Z_1Z_2}{Z_1+Z_2+Z_3}
\end{cases}
$$

이 식들은 평형 3상 시스템에서는 다음과 같이 더 간단해집니다.

$$
	\begin{align*}
&Z_A=Z_B=Z_C=Z_Y\\
&Z_1=Z_2=Z_3=Z_{\Delta}\\
&\rightarrow Z_{\Delta}=3Z_Y\text{ or }Z_Y=\displaystyle\frac{Z_{\Delta}}{3}
\end{align*}
$$

### Y 결선 전원 - Δ 결선 부하

이제 다음과 같이 전원이 Y 결선이고, 부하가 Δ 결선인 상황에 대해 알아봅시다.

(Y delta)

평형 3상 시스템을 가정하고 임피던스가 $$Z$$인 부하를 Y 결선으로 변환하면 다음과 같습니다.

(Y delta bal)

상전압이 다음과 같다고 해봅시다.

$$
\begin{cases}
			\mathbf{V}_{an}=V_m\angle\phi\\
			\mathbf{V}_{bn}=V_m\angle\left(\phi-120^{\circ}\right)\\
			\mathbf{V}_{cn}=V_m\angle\left(\phi+120^{\circ}\right)
		\end{cases}
$$

각 부하에 흐르는 전류는 다음과 같습니다.

$$
\begin{cases}
	\mathbf{I}_{L,a}=\displaystyle\frac{\mathbf{V}_{an}}{Z/3}=\displaystyle\frac{3V_m}{Z_m}\angle\left(\phi-\theta\right)\\
	\mathbf{I}_{L,b}=\displaystyle\frac{\mathbf{V}_{bn}}{Z/3}=\displaystyle\frac{3V_m}{Z_m}\angle\left(\phi-120^{\circ}-\theta\right)\\
	\mathbf{I}_{L,c}=\displaystyle\frac{\mathbf{V}_{cn}}{Z/3}=\displaystyle\frac{3V_m}{Z_m}\angle\left(\phi+120^{\circ}-\theta\right)
\end{cases}
$$

이는 선전류와 동일합니다.

### Δ 결선 전원 - Y 결선 부하

마지막으로 전원이 Δ 결선이고, 부하가 Y 결선인 경우를 살펴봅시다.

(delta Y)

평형 3상 시스템을 가정하고 임피던스가 $$Z$$인 부하를 Δ 결선으로 변환하면 다음과 같습니다.

(delta Y bal)

$$
\begin{cases}
			\mathbf{V}_{ab}=V_m\angle\phi\\
			\mathbf{V}_{bc}=V_m\angle\left(\phi-120^{\circ}\right)\\
			\mathbf{V}_{ca}=V_m\angle\left(\phi+120^{\circ}\right)
		\end{cases}
$$

각 부하에 흐르는 전류는 다음과 같습니다.

$$
\begin{cases}
	\mathbf{I}_{L,ab}=\displaystyle\frac{\mathbf{V}_{ab}}{3Z}=\displaystyle\frac{V_m}{3Z_m}\angle\left(\phi-\theta\right)\\
	\mathbf{I}_{L,bc}=\displaystyle\frac{\mathbf{V}_{bc}}{3Z}=\displaystyle\frac{V_m}{3Z_m}\angle\left(\phi-120^{\circ}-\theta\right)\\
	\mathbf{I}_{L,ca}=\displaystyle\frac{\mathbf{V}_{ca}}{3Z}=\displaystyle\frac{V_m}{3Z_m}\angle\left(\phi+120^{\circ}-\theta\right)
\end{cases}
$$

선전류는 다음과 같이 각 마디에 KCL을 적용하여 구할 수 있습니다.

$$
\begin{cases}
	\mathbf{I}_a=\mathbf{I}_{L,ab}-\mathbf{I}_{L,ca}=\displaystyle\frac{V_m}{\sqrt{3}Z_m}\angle\left(\phi-30^{\circ}-\theta\right)\\
	\mathbf{I}_b=\mathbf{I}_{L,bc}-\mathbf{I}_{L,ab}=\displaystyle\frac{V_m}{\sqrt{3}Z_m}\angle\left(\phi-150^{\circ}-\theta\right)\\
	\mathbf{I}_c=\mathbf{I}_{L,ca}-\mathbf{I}_{L,bc}=\displaystyle\frac{V_m}{\sqrt{3}Z_m}\angle\left(\phi+90^{\circ}-\theta\right)
\end{cases}
$$

---

## 최대 전력 전달

---

## 역률 개선

실제 생산되는 전력에는 사용 가능한 유효 전력과 사용할 수 없는 무효 전력이 섞여있습니다.
높은 역률은 같은 피상 전력 대비 유효 전력의 비율이 높다는 것을 의미합니다.
전기 요금은 유효 전력을 통해 계산이 됩니다.
따라서 역률이 높아야 같은 전기 요금 대비 전력 생산 단가를 낮출 수 있습니다.
더 적은 피상 전력으로도 동일한 유효 전력을 만들 수 있다는 의미이기 때문입니다.
실제로 쓰이는 부하에는 역률의 하한이 있습니다.
하한보다 낮은 역률을 가진 부하는 **역률 개선(Power Factor Correction)**이 필요합니다.

임피던스가 $$Z=R+jX$$인 부하의 역률은 다음과 같이 구할 수 있습니다.

$$
	\begin{align*}
&S=\frac{1}{2}\mathbf{V}_L\mathbf{I}_L^*=\frac{1}{2}\left\vert\mathbf{I}_L\right\vert^2Z\\
&P=\text{Re}\left[S\right]=\frac{1}{2}\left\vert\mathbf{I}_L\right\vert^2\text{Re}\left[Z\right]=\frac{1}{2}\left\vert\mathbf{I}_L\right\vert^2R\\
&\rightarrow\left(\text{PF}\right)=\frac{P}{\left\vert S\right\vert}=\frac{R}{\left\vert Z\right\vert}=\frac{R}{\sqrt{R^2+X^2}}=\frac{1}{\sqrt{1+\left(\displaystyle\frac{X}{R}\right)^2}}
\end{align*}
$$

위 식을 보면 리액턴스 값을 저항 값에 비해 작게 만들수록 역률이 증가하는 것을 알 수 있습니다.

---

## 전력 측정

이제 전력을 어떻게 측정하는지 설명하겠습니다.
전력은 **전력계(Wattmeter)**를 통해 측정합니다.

### 단상 전력 측정

먼저 단상의 경우입니다.
그림과 같이 부하 양단에 걸리는 전압을 측정하기 위해 전압계가 연결되어 있고, 부하 전류를 측정하기 위해 전류계가 연결되어 있습니다.

두 값을 측정하여 곱하면 유효 전력을 구할 수 있습니다.
유효 전력만 측정할 수 있고, 역률은 측정하지 못합니다.

### 3상 전력 측정

3상 시스템은 측정해야 하는 전압이 3개이고, 전류 또한 3개이기 때문에 전력계 또한 3개가 필요한 것으로 보입니다.
중성선에 전류가 흐르는 경우는 전력계 3개가 필요합니다.
하지만 중성선이 없는 경우는 전력계 2개만으로도 전력을 측정할 수 있습니다.

다음과 같이 $$a$$상과 $$c$$상 사이의 선간 전압 측정 및 $$a$$상의 선전류를 측정할 수 있게 전력계를 하나 설치하고, 또 $$b$$상과 $$c$$상 사이의 선간 전압 측정 및 $$b$$상의 선전류를 측정할 수 있게 전력계를 하나 설치해봅시다.

(2 watt)

상전압, 상전류, 선간 전압, 선전류가 다음과 같다고 해봅시다.

$$
\begin{align*}
	&\begin{cases}
		\mathbf{V}_{ph,a}=V_m\angle\phi_v\\
		\mathbf{V}_{ph,b}=V_m\angle\left(\phi_v-120^{\circ}\right)\\
		\mathbf{V}_{ph,c}=V_m\angle\left(\phi_v+120^{\circ}\right)
	\end{cases}\\
	&\begin{cases}
		\mathbf{I}_{ph,a}=I_m\angle\phi_i\\
		\mathbf{I}_{ph,b}=I_m\angle\left(\phi_i-120^{\circ}\right)\\
  \mathbf{I}_{ph,c}=I_m\angle\left(\phi_i+120^{\circ}\right)
	\end{cases}\\
	&\begin{cases}
		\mathbf{V}_{ac}=V_l\angle\phi_{vl}\\
		\mathbf{V}_{bc}=V_l\angle\left(\phi_{vl}-60^{\circ}\right)
	\end{cases}\\
	&\begin{cases}
		\mathbf{I}_a=I_l\angle\phi_{il}\\
		\mathbf{I}_b=I_l\angle\left(\phi_{il}-120^{\circ}\right)
	\end{cases}
\end{align*}
$$

이때 각 전력계가 측정하는 유효 전력은 다음과 같습니다.

$$
	\begin{cases}
		P_1=\text{Re}\left[S_1\right]=\text{Re}\left[\displaystyle\frac{1}{2}\mathbf{V}_{ac}\mathbf{I}_a^*\right]=\displaystyle\frac{V_lI_l}{2}\cos\left(\phi_{vl}-\phi_{il}\right)\\
		P_2=\text{Re}\left[S_2\right]=\text{Re}\left[\displaystyle\frac{1}{2}\mathbf{V}_{bc}\mathbf{I}_b^*\right]=\displaystyle\frac{V_lI_l}{2}\cos\left(\phi_{vl}-\phi_{il}+60^{\circ}\right)
	\end{cases}
$$

두 전력의 합은 다음과 같습니다.

$$
\begin{align*}
	P_1+P_2&=\frac{V_lI_l}{2}\cos\left(\phi_{vl}-\phi_{il}\right)+\frac{V_lI_l}{2}\cos\left(\phi_{vl}-\phi_{il}+60^{\circ}\right)\\
	&=\frac{\sqrt{3}}{2}V_lI_l\cos\left(\phi_{vl}-\phi_{il}+30^{\circ}\right)
\end{align*}
$$

먼저 Y 결선된 전원에 대해 생각해봅시다.
이 경우에 상전압과 선간 전압은 다음의 관계에 있습니다.

$$
\begin{cases}
	\mathbf{V}_{ac}=\mathbf{V}_{ph,a}-\mathbf{V}_{ph,c}&\rightarrow V_l\angle\phi_{vl}=\sqrt{3}V_m\angle\left(\phi_v-30^{\circ}\right)\\	\mathbf{V}_{bc}=\mathbf{V}_{ph,b}-\mathbf{V}_{ph,c}&\rightarrow V_l\angle\left(\phi_{vl}-60^{\circ}\right)=\sqrt{3}V_m\angle\left(\phi_v-90^{\circ}\right)
\end{cases}
$$

선간 전압의 진폭과 위상은 다음과 같이 나타낼 수 있습니다.

$$
\begin{cases}
		V_l=\sqrt{3}V_m\\
		\phi_{vl}=\phi_v-30^{\circ}
	\end{cases}
$$

상전류와 선전류는 같으므로 다음과 같습니다.

$$
\begin{cases}
		I_l=I_m\\
		\phi_{il}=\phi_i
	\end{cases}
$$

이전에 구한 전력 합에 대입하면 다음과 같습니다.

$$
\begin{align*}
P_1+P_2&=\frac{\sqrt{3}}{2}V_lI_l\cos\left(\phi_{vl}-\phi_{il}+30^{\circ}\right)\\
&=\frac{3}{2}V_mI_m\cos\left(\phi_v-\phi_i\right)
\end{align*}
$$

상전압과 상전류의 위상차를 $$\phi=\phi_v-\phi_i$$라고 하면 다음과 같습니다.

$$
P_1+P_2=\frac{3}{2}V_mI_m\cos\phi
$$

[앞](#평형-3상-시스템)서 언급한 3상 시스템의 전력과 동일합니다.

다음으로 Δ 결선된 전원의 경우를 살펴봅시다.
상전압과 선간 전압이 같으므로 다음과 같습니다.

$$
\begin{cases}
		V_l=V_m\\
		\phi_{vl}=\phi_v
	\end{cases}
$$

상전류와 선전류는 다음의 관계에 있습니다.

$$
\begin{cases}
	\mathbf{I}_a=\mathbf{I}_{ph,a}-\mathbf{I}_{ph,c}&\rightarrow I_l\angle\phi_{il}=\sqrt{3}I_m\angle\left(\phi_i-30^{\circ}\right)\\
	\mathbf{I}_b=\mathbf{I}_{ph,b}-\mathbf{I}_{ph,a}&\rightarrow I_l\angle\left(\phi_{il}-120^{\circ}\right)=\sqrt{3}I_m\angle\left(\phi_i-150^{\circ}\right)
\end{cases}
$$

선전류의 진폭과 위상은 다음과 같습니다.

$$
\begin{cases}
	I_l=\sqrt{3}I_m\\
	\phi_{il}=\phi_i-30^{\circ}
\end{cases}
$$

이전에 구한 전력 합에 대입하면 다음과 같습니다.

$$
\begin{align*}
P_1+P_2&=\frac{\sqrt{3}}{2}V_lI_l\cos\left(\phi_{vl}-\phi_{il}+30^{\circ}\right)\\
&=\frac{3}{2}V_mI_m\cos\left(\phi_v-\phi_i\right)
\end{align*}
$$

상전압과 상전류의 위상차를 $$\phi=\phi_v-\phi_i$$라고 하면 다음과 같습니다.

$$
P_1+P_2=\frac{3}{2}V_mI_m\cos\phi
$$

이 또한 [앞](#평형-3상-시스템)서 언급한 3상 시스템의 전력과 동일합니다.
이렇게 전력계를 2개만 사용하여 측정하는 방법을 **2 전력계법(Two Wattmeter Method)**이라고 합니다.

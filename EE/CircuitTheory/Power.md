# 전력

---

## 전력

**전력(Power)**이란 단위 시간당 공급되거나 소비되는 전기 에너지를 의미합니다.

$$
p=\frac{dW}{dt}
$$

단위는 와트[W]입니다. 위 식은 전압과 전류를 이용해 표현할 수 있습니다.
우선 전압은 단위 전하가 갖는 전기 퍼텐셜 에너지입니다.

$$
v=\frac{dW}{dq}
$$

전류는 단위 시간당 어느 단면을 통과하는 전하의 총량입니다.

$$
i=\frac{dq}{dt}
$$

연쇄 법칙을 이용하면 다음과 같습니다.

$$
p=\frac{dW}{dt}=\frac{dW}{dq}\frac{dq}{dt}=vi
$$

따라서 전력은 전압과 전류의 곱으로 표현되는 것을 알 수 있습니다.
옴의 법칙을 이용하여 다음과 같이 표현할 수도 있습니다.

$$
\begin{align*}
&v=iR\\
&p=vi=i^2R\\
&\text{or}\\
&p=vi=\frac{v^2}{R}
\end{align*}
$$

## 순시 전력

실제로 발전소에서 공급되는 전력을 살펴보면, 전압과 전류의 위상이 일반적으로 다릅니다.
다음의 사인형 전압과 전류를 생각해봅시다. 

$$
\begin{align*}
&v(t)=V_m\cos\left(\omega t+\theta_v\right)\\
&i(t)=I_m\cos\left(\omega t+\theta_i\right)
\end{align*}
$$

계산상의 편의를 위해 $$\theta_i$$만큼 평행 이동 시켜봅시다.

$$
\begin{align*}
&v(t)=V_m\cos\left(\omega t+\theta_v-\theta_i\right)\\
&i(t)=I_m\cos\left(\omega t\right)
\end{align*}
$$

위상차를 $$\theta=\theta_v-\theta_i$$라고 하고, 전력을 구하면 다음과 같습니다.

$$
\begin{align*}
&p(t)=v(t)i\left(t\right)=V_mI_m\cos\left(\omega t+\theta\right)\cos\left(\omega t\right)\\
\end{align*}
$$

다음의 삼각 함수 공식을 이용하여 전개해봅시다.

$$
\begin{align*}
		&\cos\alpha\cos\beta=\frac{1}{2}\cos\left(\alpha-\beta\right)+\frac{1}{2}\cos\left(\alpha+\beta\right)\\
&p(t)=\frac{V_mI_m}{2}\cos\theta+\frac{V_mI_m}{2}\cos\left(2\omega t+\theta\right)
\end{align*}
$$

두번째 항을 다음의 삼각 함수 공식을 이용하여 전개해봅시다.

$$
\begin{align*}
&\cos\left(\alpha+\beta\right)=\cos\alpha\cos\beta-\sin\alpha\sin\beta\\
&p(t)=\frac{V_mI_m}{2}\cos\theta+\frac{V_mI_m}{2}\left(\cos\theta\cos\left(2\omega t\right)-\sin\theta\sin\left(2\omega t\right)\right)
\end{align*}
$$

코사인과 사인으로 각각 묶으면 다음과 같습니다.

$$
p(t)=\frac{V_mI_m}{2}\cos\theta\left(1+\cos\left(2\omega t\right)\right)-\frac{V_mI_m}{2}\sin\theta\sin\left(2\omega t\right)
$$

이 양을 통해 특정 시각에서의 전력을 확인할 수 있고, 이를 **순시 전력(Instantaneous Power)**이라고 합니다.

---

## RMS (제곱-평균-제곱근)


---

## 유효 전력과 무효 전력

### 유효 전력

순시 전력을 다시 살펴봅시다.

$$
p(t)=\frac{V_mI_m}{2}\cos\theta\left(1+\cos\left(2\omega t\right)\right)-\frac{V_mI_m}{2}\sin\theta\sin\left(2\omega t\right)
$$

순시 전력의 평균을 구하면 다음과 같습니다.

$$
P=\frac{1}{T}\int_T p(t)dt=\frac{V_mI_m}{2}\cos\theta
$$

삼각 함수 항의 평균은 $$0$$이므로 위와 같습니다.
이 양을 **유효 전력(Real Power)**이라고 합니다.
실제로 부하로 공급되는 전력을 의미합니다.
다른 형태의 에너지로 전환될 수 있는 양입니다.
**평균 전력(Average Power)**이라고도 합니다.

### 무효 전력

위 식을 다시 살펴봅시다.

$$
p(t)=\frac{V_mI_m}{2}\cos\theta\left(1+\cos\left(2\omega t\right)\right)-\frac{V_mI_m}{2}\sin\theta\sin\left(2\omega t\right)
$$

유효 전력을 이용하면 다음과 같이 쓸 수 있습니다.

$$
p(t)=P\left(1+\cos\left(2\omega t\right)\right)-\frac{V_mI_m}{2}\sin\theta\sin\left(2\omega t\right)
$$

두번째 항은 존재는 하지만, 평균이 $$0$$이므로 부하에 전달되는 전력이 없습니다.
주파수 항을 제외한 나머지 부분을 **무효 전력(Reactive Power)**이라고 합니다.

$$
Q=\frac{V_mI_m}{2}\sin\theta
$$

단위는 [VAR]입니다.
이 양은 부하에 전달되지 않고, 회로 내에서 전원과 에너지 저장 소자(인덕터, 축전기) 사이에서 계속 순환하는 양입니다.
유효 전력과 무효 전력을 이용하면 순시 전력을 다음과 같이 나타낼 수 있습니다.

$$
p(t)=P\left(1+\cos\left(2\omega t\right)\right)-Q\sin\left(2\omega t\right)
$$

---

## 복소 전력

### 피상 전력

([위상자](./Phasor.md) 표현이 익숙하지 않으신 분은 해당 문서를 참고 바랍니다.)



$$
\begin{align*}
		&\mathbf{V}=V_m\angle\theta_v\\
		&\mathbf{I}=I_m\angle\theta_i
	\end{align*}
$$

---

## 최대 전력 전달 조건

테브난 정리에 따라 회로를 다음과 같이 변환할 수 있습니다.
이 상황에서 부하로 전달되는 전력이 최대가 되려면 어떤 조건이 필요한지 알아봅시다.

### 저항성 부하

먼저 저항으로만 구성된 부하에 대한 상황입니다.
전원의 전압을 정현파 전압이라고 가정해봅시다.

$$
\mathbf{V}=V_m\angle\theta
$$

부하에 걸리는 전압은 전압 분배에 의해 다음과 같습니다.

$$
\mathbf{V}_L=\frac{R_L}{R_{Th}+R_L}\mathbf{V}
$$

부하에 흐르는 전류는 다음과 같습니다.

$$
\mathbf{I}_L=\frac{\mathbf{V}_L}{R_{Th}+R_L}
$$

부하로 전달되는 피상 전력은 다음과 같습니다.

$$
\begin{align*}
		\mathbf{S}_L&=\frac{1}{2}\mathbf{V}_L\mathbf{I}_L^*\\
		&=\frac{1}{2}\frac{R_L}{R_{Th}+R_L}\mathbf{V}_L\frac{\mathbf{V}_L^*}{R_{Th}+R_L}\\
		&=\frac{V_m^2R_L}{2\left(R_{Th}+R_L\right)^2}
	\end{align*}
$$

이 양은 실수이므로 유효 전력과 같습니다.

$$
P_L=\frac{V_m^2R_L}{2\left(R_{Th}+R_L\right)^2}
$$

이 식이 바로 부하로 전달되는 전력입니다.
이 식이 언제 최소가 되는지 알아내기 위해 양 변을 부하 저항에 대해 미분하면 다음과 같습니다.

$$
\frac{dP_L}{dR_L} = \frac{V_m^2 \left(R_{Th} - R_L\right)}{2 \left(R_{Th} + R_L\right)^3}
$$

이 식이 $$0$$인 조건은 다음과 같습니다.

$$
\frac{dP_L}{dR_L}=0\ \ \ \text{if }\ R_L=R_{Th}
$$

따라서 회로의 테브난 등가 저항과 부하 저항이 같을 때, 부하로 전달되는 전력이 최대가 되는 것을 알 수 있습니다.

### 임피던스 부하

다음으로 일반적인 임피던스 부하에 대해 살펴봅시다.
부하에 걸리는 전압은 다음과 같습니다.

$$
\mathbf{V}_L=\frac{R_L+jX_L}{R_{Th}+R_L+j\left(X_{Th}+X_L\right)}\mathbf{V}
$$

부하에 흐르는 전류는 다음과 같습니다.

$$
\mathbf{I}_L=\frac{\mathbf{V}}{R_{Th}+R_L+j\left(X_{Th}+X_L\right)}
$$

부하로 전달되는 피상 전력은 다음과 같습니다.

$$
\begin{align*}
		\mathbf{S}_L&=\frac{1}{2}\mathbf{V}_L\mathbf{I}_L^*\\
		&=\frac{1}{2}\frac{R_L+jX_L}{R_{Th}+R_L+j\left(X_{Th}+X_L\right)}\mathbf{V}\frac{\mathbf{V}^*}{R_{Th}+R_L-j\left(X_{Th}+X_L\right)}\\
		&=\frac{V_m^2\left(R_L+jX_L\right)}{2\left(\left(R_{Th}+R_L\right)^2+\left(X_{Th}+X_L\right)^2\right)}
	\end{align*}
$$

이 식에서 유효 전력은 다음과 같습니다.

$$
P=\frac{V_m^2R_L}{2\left(\left(R_{Th}+R_L\right)^2+\left(X_{Th}+X_L\right)^2\right)}
$$

이 식에 언제 최소가 되는지 알아보기 위해 부하 저항 및 부하 리액턴스에 대해 각각 편미분하면 다음과 같습니다.

$$
\begin{cases}
		\frac{\partial P_L}{\partial R_L}
		= \frac{V_m^2 \left(\left(R_{Th} + R_L\right)^2 + \left(X_{Th} + X_L\right)^2 - 2R_L(R_{Th} + R_L) \right)}{2\left(\left(R_{Th} + R_L\right)^2 + \left(X_{Th} + X_L\right)^2\right)^2}\\
		\frac{\partial P_L}{\partial X_L}
		= \frac{-V_m^2 R_L (X_{Th} + X_L)}{\left(\left(R_{Th} + R_L\right)^2 + \left(X_{Th} + X_L\right)^2\right)^2}
		\end{cases}
$$

각 식이 $$0$$이 될 조건은 다음과 같습니다.

$$
\begin{cases}
		R_L=\sqrt{R_{Th}^2+\left(X_{Th}+X_L\right)^2}\\
		X_L=-X_{Th}
		\end{cases}
$$

두 조건을 종합하여 정리하면 다음과 같습니다.

$$
\begin{align*}
&R_L=R_{Th}\ \ \ \text{since }X_L=-X_{Th}\\
&\rightarrow Z_L=Z_{Th}^*
\end{align*}
$$

일반적인 임피던스 부하에 대해서는 부하 임피던스를 등가 임피던스의 켤레 값으로 조정하면 부하에 전달되는 전력이 최대가 되는 것을 알 수 있습니다.

### 제약 조건이 있는 경우

제약 조건에 의해 부하 임피던스를 우리가 원하는 값으로 맞추지 못하는 경우가 있습니다.

(1) 부하 저항 및 리액턴스의 범위가 제한된 경우

이런 경우는 우선, $$X_L$$를 $$-X_{Th}$$에 최대한 가깝게 조정합니다.
이후에 $$R_L$$을 $$\sqrt{R_{Th}^2+\left(X_{Th}+X_L\right)^2}$$에 최대한 가깝게 조정합니다.

(2) 부하 임피던스의 위상을 바꿀 수 없는 경우
임피던스를 극형식으로 나타내면 다음과 같습니다.

$$
\begin{align*}
		Z_L&=R_L+jX_L\\
		&=\sqrt{R_L^2+X_L^2}\exp\left(j\tan^{-1}\left(\frac{X_L}{R_L}\right)\right)
	\end{align*}
$$



크기$$\left(\sqrt{R_L^2+X_L^2\right})$$는 조정 가능하고, 비율$$\left(\frac{X_L}{R_L}\right)$$은 고정된 경우입니다.
이 경우는 $$\left|Z_L\right|$$을 $$\left|Z_{Th}\right|$$와 같도록 조정합니다.

### 임피던스 정합

이러한 튜닝 과정을 일반적으로 **[임피던스 정합]()**이라고 합니다.
부하로 전달되는 전력을 최대화하는 것이 목적입니다.
자세한 내용은 해당 문서 참고 바랍니다.

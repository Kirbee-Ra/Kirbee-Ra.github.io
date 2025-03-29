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
		&v\left(t\right)=V_m\cos\left(\omega t+\theta_v\right)\\
		&i\left(t\right)=I_m\cos\left(\omega t+\theta_i\right)
	\end{align*}
$$

계산상의 편의를 위해 $$\theta_i$$만큼 평행 이동 시켜봅시다.

$$
\begin{align*}
		&v\left(t\right)=V_m\cos\left(\omega t+\theta_v-\theta_i\right)\\
		&i\left(t\right)=I_m\cos\left(\omega t\right)\\
	\end{align*}
$$

위상차를 $$\theta=\theta_v-\theta_i$$라고 하고, 전력을 구하면 다음과 같습니다.

$$
\begin{align*}
		&p\left(t\right)=v\left(t\right)i\left(t\right)=V_mI_m\cos\left(\omega t+\theta\right)\cos\left(\omega t\right)\\
	\end{align*}
$$

다음의 삼각 함수 공식을 이용하여 전개해봅시다.

$$
\begin{align*}
		&\cos\alpha\cos\beta=\frac{1}{2}\cos\left(\alpha-\beta\right)+\frac{1}{2}\cos\left(\alpha+\beta\right)\\
		&p\left(t\right)=\frac{V_mI_m}{2}\cos\theta+\frac{V_mI_m}{2}\cos\left(2\omega t+\theta\right)
	\end{align*}
$$

두번째 항을 다음의 삼각 함수 공식을 이용하여 전개해봅시다.

$$
\begin{align*}
&\cos\left(\alpha+\beta\right)=\cos\alpha\cos\beta-\sin\alpha\sin\beta\\
    &p\left(t\right)=\frac{V_mI_m}{2}\cos\theta+\frac{V_mI_m}{2}\left(\cos\theta\cos\left(2\omega t\right)-\sin\theta\sin\left(2\omega t\right)\right)
\end{align*}
$$

코사인과 사인으로 각각 묶으면 다음과 같습니다.

$$
p\left(t\right)=\frac{V_mI_m}{2}\cos\theta\left(1+\cos\left(2\omega t\right)\right)-\frac{V_mI_m}{2}\sin\theta\sin\left(2\omega t\right)
$$

이 양을 통해 특정 시각에서의 전력을 확인할 수 있고, 이를 **순시 전력(Instantaneous Power)**이라고 합니다.

---

## RMS (제곱-평균-제곱근)


---

## 유효 전력과 무효 전력

### 유효 전력

순시 전력을 다시 살펴봅시다.

$$
p\left(t\right)=\frac{V_mI_m}{2}\cos\theta\left(1+\cos\left(2\omega t\right)\right)-\frac{V_mI_m}{2}\sin\theta\sin\left(2\omega t\right)
$$

순시 전력의 평균을 구하면 다음과 같습니다.

$$
P=\frac{1}{T}\int_T p\left(t\right)dt=\frac{V_mI_m}{2}\cos\theta
$$

삼각 함수 항의 평균은 $$0$$이므로 위와 같습니다.
이 양을 **유효 전력(Real Power)**이라고 합니다.
실제로 부하로 공급되는 전력을 의미합니다.
다른 형태의 에너지로 전환될 수 있는 양입니다.
**평균 전력(Average Power)**이라고도 합니다.

### 무효 전력

위 식을 다시 살펴봅시다.

$$
p\left(t\right)=\frac{V_mI_m}{2}\cos\theta\left(1+\cos\left(2\omega t\right)\right)-\frac{V_mI_m}{2}\sin\theta\sin\left(2\omega t\right)
$$

유효 전력을 이용하면 다음과 같이 쓸 수 있습니다.

$$
p\left(t\right)=P\left(1+\cos\left(2\omega t\right)\right)-\frac{V_mI_m}{2}\sin\theta\sin\left(2\omega t\right)
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
p\left(t\right)=P\left(1+\cos\left(2\omega t\right)\right)-Q\sin\left(2\omega t\right)
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


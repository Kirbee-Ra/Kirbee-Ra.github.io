# 전력

---

## 전력

**전력(Power)**이란 단위 시간당 공급되거나 소비되는 전기 에너지를 의미합니다.

$$
p=\frac{dW}{dt}
$$

위 식은 전압과 전류를 이용해 표현할 수 있습니다. 우선 전압은 단위 전하가 갖는 전기 퍼텐셜 에너지입니다.

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

따라서 전력은 전압과 전류의 곱으로 표현되는 것을 알 수 있습니다. 옴의 법칙을 이용하여 다음과 같이 표현할 수도 있습니다.

$$
\begin{align*}
&v=iR\\
&p=vi=i^2R\\
&\text{or}\\
&p=vi=\frac{v^2}{R}
\end{align*}
$$

---

## 복소 전력
실제로 발전소에서 공급되는 전력을 살펴보면, 전압과 전류의 위상이 일반적으로 다릅니다. 다음의 사인형 전압과 전류를 생각해봅시다. 

$$
\begin{align*}
		&v\left(t\right)=V_m\cos\left(\omega t+\theta_v\right)\\
		&i\left(t\right)=I_m\cos\left(\omega t+\theta_i\right)
	\end{align*}
$$

계산상의 편의를 위해 $\theta_i$만큼 평행 이동 시켜봅시다.

$$
\begin{align*}
		&v\left(t\right)=V_m\cos\left(\omega t+\theta_v\right)\\
		&i\left(t\right)=I_m\cos\left(\omega t+\theta_i\right)\\
	\end{align*}
$$

위상차를 $\theta=\theta_v-\theta_i$라고 하고, 전력을 구하면 다음과 같습니다.

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

([위상자](./Phasor.md) 표현이 익숙하지 않으신 분은 해당 문서를 참고 바랍니다.)

$$
\begin{align*}
		&\mathbf{V}=V_m\angle\theta_v\\
		&\mathbf{I}=I_m\angle\theta_i
	\end{align*}
$$


### 피상 전력

### 유효 전력

### 무효 전력

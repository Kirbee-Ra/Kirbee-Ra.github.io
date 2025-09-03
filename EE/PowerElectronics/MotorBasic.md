전동기의 기초
=

---

## 목차

---

## 전동기

**전동기(Motor)**는 전기 에너지를 역학적 에너지로 변환하는 장치입니다.
주로 전류를 흘려서 회전 운동 에너지로 변환합니다.
전동기의 원리를 공부하기 위해서는 기초적인 전자기학 및 회전 운동에 대해 공부할 필요가 있습니다.

---

## 기초 전자기 이론

전동기 공부에 필요한 기초 전자기학을 먼저 살펴봅시다.

### 자속

그림과 같이 솔레노이드에 전류를 흘린다고 생각해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/솔레노이드.png" alt="솔레노이드" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 솔레노이드)
  </figcaption>
</figure>

솔레노이드의 단면은 다음과 같이 나타낼 수 있습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/솔레노이드 단면.png" alt="솔레노이드 단면" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 솔레노이드의 단면)
  </figcaption>
</figure>

직사각형 형태의 단면 $$S$$를 생각해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/솔레노이드 단면 S.png" alt="솔레노이드 단면 S" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 단면 S를 고려한 솔레노이드의 단면)
  </figcaption>
</figure>

이 단면 $$S$$에 대해 암페어 법칙을 적용하면 다음과 같습니다.

$$
\oint_{\partial S} \mathbf{B}\cdot d\mathbf{l}=\mu\int_S \mathbf{J}\cdot d\mathbf{a}
$$

솔레노이드 외부 자기장은 $$\mathbf{0}$$이고, 내부에서 세로 경로는 자기장과의 내적이 $$0$$이므로 다음과 같습니다.

$$
\begin{align*}
	&Bl=\mu NI\\
	&\rightarrow B=\frac{\mu NI}{l}
\end{align*}
$$

이제 다음과 같은 단면 $$A$$를 고려해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/솔레노이드 단면 A.png" alt="솔레노이드 단면 A" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 단면 A를 고려한 솔레노이드)
  </figcaption>
</figure>

단면 $$A$$를 통과하는 **자속(Magnetic Flux 또는 Flux)**은 다음과 같이 나타낼 수 있습니다.

$$
\begin{align*}
	\Phi&=\int_A \mathbf{B}\cdot d\mathbf{a}\\
	&=BA\\
	&=\frac{\mu NA}{l}I
\end{align*}
$$

자속은 특정 단면을 통과하는 자기장선의 양을 의미합니다.
솔레노이드 전체를 통과하는 자기장선의 양은 **쇄교 자속(Flux Linkage)**라고 하며 다음과 같습니다.

$$
\Lambda=N\Phi
$$

$$1$$ 턴 당 통과하는 자속이 있고, 솔레노이드는 총 $$N$$ 턴 감겨있으므로 자속에 $$N$$을 곱하면 쇄교 자속이 됩니다.

### 인덕턴스

**인덕턴스(Inductance)**는 인덕터에 흐르는 단위 전류 당 생성되는 자속의 양을 의미합니다.

$$
L=\frac{\Phi}{I}
$$

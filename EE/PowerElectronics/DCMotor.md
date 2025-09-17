직류 전동기
=

---

## 목차

- [직류 전동기](#dc-motor)
- [직류 전동기 모델링](#직류-전동기-모델링)

---

<h2 id="dc-motor">직류 전동기</h2>

**직류 전동기(DC Motor)**는 직류 전력를 공급받아 동력을 생성하는 전동기입니다.
직류 전동기의 구조는 다음과 같습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/직류전동기.png" alt="직류전동기" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 직류 전동기)
  </figcaption>
</figure>

먼저 **계자 권선(Field Winding)**에 전류를 흘려서 외부 자기장을 형성합니다.
다음으로 **전기자 권선(Armature Winding)**에 전류를 흘리면 도선이 자기력을 받아 회전합니다.

---

## 직류 전동기 모델링

### 직류 전동기의 등가 회로

직류 전동기의 동작 원리 이해 및 제어기 설계를 위해 등가 회로로 모델링할 필요가 있습니다.
전기자의 단자에 전압을 걸면 전기자 권선에 전류가 흐릅니다.
전기자 권선은 인덕턴스와 기생 저항으로 모델링할 수 있습니다.
그리고 전기자 권선이 회전하면 권선의 단면을 통과하는 자속이 계속 변합니다.
패러데이 법칙에 의해 전기자 권선에는 또 다른 전압이 유도됩니다.
이를 **역기전력(Back EMF)**이라고 합니다.
이를 통해 다음과 같이 등가 회로로 표현할 수 있습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/직류전동기등가회로.png" alt="직류전동기등가회로" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 직류 전동기의 등가 회로)
  </figcaption>
</figure>

전기자 전류 $$i_a$$가 전기자 권선의 인덕턴스 $$L_a$$와 기생 저항 $$R_a$$를 따라 흐르며, 역기전력 $$E_a$$가 유도됩니다.

### 역기전력

길이가 $$l$$인 도선이 균일한 자속 밀도 $$B$$의 자기장 내에서 속도 $$v$$로 운동한다고 해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/자기장도선.png" alt="자기장도선" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 자기장도선)
  </figcaption>
</figure>

이때 도선에 유도된 기전력은 다음과 같습니다.

$$
\mathcal{E}=Blv
$$

이제 다음과 같이 세로 길이가 $$l$$인 직사각형의 전류 고리가 균일한 자속 밀도 $$B$$의 자기장 내에서 선속도 $$v$$로 회전한다고 해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/자기장고리.png" alt="자기장고리" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 자기장내에서 회전하는 전류 고리)
  </figcaption>
</figure>

도선에 유도된 기전력은 이전과 같습니다.

$$
\mathcal{E}=Blv
$$

회전축으로부터 고리의 끝 부분까지의 길이를 $$r$$이라고 하면, 각속도 $$\omega_m$$을 이용하여 다음과 같이 나타낼 수 있습니다.

$$
\mathcal{E}=Blr\omega_m
$$

자속 밀도는 다음과 같이 계자 자속 $$\Phi_f$$와 도선의 단면적 $$A$$를 이용하여 나타낼 수 있습니다.

$$
B=\frac{\Phi_f}{A}
$$

기전력은 다음과 같습니다.

$$
\mathcal{E}=\frac{\Phi_f lr\omega_m}{A}
$$

$$A$$와 $$lr$$은 차원이 같으므로 $$\frac{lr}{A}$$을 상수 $$k_e$$로 나타낼 수 있습니다.

$$
\mathcal{E}=k_e\Phi_f\omega_m
$$

상수 $$k_e$$는 기전력 상수로 단위는 $$\text{V}\cdot\text{s/rad/Wb}$$입니다.
일반적으로 계자 자속은 일정합니다.
따라서 기전력을 다음과 같이 나타낼 수 있습니다.

$$
\mathcal{E}=K_e\omega_m\ \ \ \text{where }K_e=k_e\Phi_f
$$

이 기전력을 역기전력이라고 하며, 전기자 단자 전압과 반대 극성으로 유도되었기 때문에 반대를 의미하는 '역'이 붙습니다.

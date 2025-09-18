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

**고정자(Stator)**는 전동기 내에서 고정된 부분입니다.
고정자에는 **계자(Field Magnet)**가 연결되어 자기장을 형성합니다.
영구자석보다는 **계자 권선(Field Winding)**을 감아서 전자석의 형태로 자기장을 형성합니다.
이 계자 권선에 전류를 흘려서 외부 자기장을 형성합니다.
형성된 자기장의 자속을 **계자 자속(Field Flux)**라고 하며, 보통 일정하게 유지합니다.
고정자에서는 전기 에너지가 자기 에너지로 전환됩니다.

다음으로 **회전자(Rotor)**는 전동기 내에서 회전하는 부분입니다.
회전자에는 **전기자 권선(Armature Winding)**이 연결되어 있습니다.
이 전기자 권선에 전류를 흘리면 도선이 자기력을 받아 회전합니다.
회전자에서는 자기 에너지가 역학적 에너지로 전환됩니다.

권선의 단면을 통과하는 자속이 최대가 되는 순간 전류의 방향이 바뀝니다.
따라서 자기력을 반대 방향으로 받게 되고, 지속적인 회전을 할 수 없습니다.
이를 방지하기 위해 중간에 전류의 방향을 교정할 필요가 있습니다.
직류 전력을 공급하므로 전류의 방향을 입력단에서 바꿀 수는 없습니다.
그러므로 **정류자(Commutator)**를 이용하여 그림과 같이 자속이 최대가 되기 전후의 전류가 동일한 방향으로 흐를 수 있게 해줍니다.
정류자는 권선과 연결되어 있으며, 부분적으로 끊어져 있는 구조입니다.
그리고 외부 전원으로부터 정류자로 전류가 흐르도록 연결해주는 부품이 **브러시(Brush)**입니다.
이로 인해 직류 전력을 공급 받아 교류 전류를 유도할 수 있습니다.

직류 전동기는 토크와 속도를 제어하기 쉽다는 장점이 있습니다.
하지만 정류자와 브러시를 정기적으로 보수해야 하고, 고속 동작에는 적합하지 않다는 단점이 있습니다.

직류 전동기보다는 **교류 전동기(AC Motor)**나 **BLDC 전동기(Brushless DC Motor)**를 많이 사용합니다.
이들의 동작 및 설계를 위해서는 직류 전동기를 먼저 공부할 필요가 있습니다.

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

전기자 전류 $$i_a$$가 전기자 권선의 인덕턴스 $$L_a$$와 기생 저항 $$R_a$$를 따라 흐르며, 역기전력 $$\mathcal{E}_a$$가 유도됩니다.

### 역기전력

길이가 $$l$$인 도선이 균일한 자속 밀도 $$B$$의 자기장 내에서 속도 $$v$$로 운동한다고 해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/자기장도선.png" alt="자기장도선" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 자기장내에서 운동하는 도선)
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

고리에 유도된 기전력은 이전과 같습니다.

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

$$A$$와 $$lr$$은 차원이 같으므로 $$\displaystyle\frac{lr}{A}$$을 상수 $$k_e$$로 나타낼 수 있습니다.

$$
\mathcal{E}=k_e\Phi_f\omega_m
$$

상수 $$k_e$$는 기전력 상수입니다.
일반적으로 계자 자속은 일정합니다.
따라서 기전력을 다음과 같이 나타낼 수 있습니다.

$$
\mathcal{E}=K_e\omega_m\ \ \ \text{where }K_e=k_e\Phi_f
$$

$$K_T$$는 기전력 상수이며, 단위가 $$\text{V}\cdot\text{s/rad}$$입니다.
이 기전력을 역기전력이라고 하며, 전기자 단자 전압과 반대 극성으로 유도되었기 때문에 반대를 의미하는 '역'이 붙습니다.

### 토크

그림과 같이 자속 밀도 $$B$$인 균일한 자기장 내에 있는 길이가 $$l$$인 도선에 전류 $$i$$를 흘린다고 생각해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/자기장도선2.png" alt="자기장도선2" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 자기장 내에서 전류가 흐르는 도선)
  </figcaption>
</figure>

이때 도선이 받는 자기력은 다음과 같습니다.

$$
F=Bil
$$

이제 다음과 같이 세로 길이가 $$l$$인 직사각형의 전류 $$i_a$$가 흐르는 고리가 균일한 자속 밀도 $$B$$의 자기장 내에 있다고 해봅시다.


<figure style="text-align: center;">
  <img src="./PEFigure/자기장고리2.png" alt="자기장고리2" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 자기장내에서 전류가 흐르는 고리)
  </figcaption>
</figure>

고리가 받는 자기력은 이전과 같습니다.

$$
F=Bi_al
$$

회전축으로부터 고리의 끝 부분까지의 길이를 $$r$$이라고 하면, 고리에 작용하는 토크는 다음과 같습니다.

$$
T=rBi_al
$$

자속 밀도는 다음과 같이 계자 자속 $$\Phi_f$$와 도선의 단면적 $$A$$를 이용하여 나타낼 수 있습니다.

$$
B=\frac{\Phi_f}{A}
$$

자기력에 의한 토크는 다음과 같습니다.

$$
T=\frac{r\Phi_fi_al}{A}
$$

$$A$$와 $$lr$$은 차원이 같으므로 $$\displaystyle\frac{lr}{A}$$을 상수 $$k_T$$으로 나타낼 수 있습니다.

$$
T=k_T\Phi_fi_a
$$

일반적으로 계자 자속은 일정합니다.
따라서 토크를 다음과 같이 나타낼 수 있습니다.

$$
T=K_Ti_a\ \ \ \text{where }K_T=k_T\Phi_f
$$

$$K_T$$는 토크 상수이며, 단위가 $$\text{N}\cdot\text{m/A}$$입니다.
SI 단위계에서는 기전력 상수와 토크 상수가 동일합니다.

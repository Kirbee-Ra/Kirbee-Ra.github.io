컨버터
=

---

## 목차
- [컨버터](#converter)
- [스위칭 전력 변환 회로](#스위칭-전력-변환-회로)
- [제어기](#제어기)
- [컨버터의 동작 모드](#컨버터의-동작-모드)

---

<h2 id="converter">컨버터</h2>

다음 시스템을 살펴봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/컨버터.png" alt="컨버터" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 컨버터의 구조)
  </figcaption>
</figure>

입력된 전압을 스위칭 네트워크를 통해 변압합니다.
그리고 저주파 필터를 거쳐 부하로 출력합니다.
여기서 전압 레벨을 변환하는 부분을 **파워 스테이지(Power Stage)**라고 합니다.
입력단에서 전압 변동 혹은 노이즈가 생길 수 있고, 부하가 순수한 저항성 부하가 아니거나 부하 변동이 생길 수 있습니다.
이러한 외란이 시스템에 입력돼도 출력 전압을 일정하게 유지할 수 있도록 제어기가 필요합니다.
파워 스테이지와 제어기를 통틀어 **컨버터(Converter)**라고 합니다.

---

## 스위칭 레귤레이터

### 스위칭 파워-폴

파워 스테이지에서 전력 변환을 어떻게 수행하는지 알아봅시다.
기본적으로 다음과 같은 스위칭 파워-폴로 구성됩니다.

<figure style="text-align: center;">
  <img src="./PEFigure/스위칭파워폴.png" alt="스위칭파워폴" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 스위칭 파워-폴)
  </figcaption>
</figure>

이는 컨버터의 종류에 따라 구조가 조금씩 다르지만 전력 변환 원리는 동일합니다.
트랜지스터를 구동하면 전력이 전달되고, 끄면 전달되지 않습니다.
다이오드 양단의 전압은 다음과 같이 나타납니다.

<figure style="text-align: center;">
  <img src="./PEFigure/다이오드전압.png" alt="다이오드전압" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 다이오드 양단의 전압 파형)
  </figcaption>
</figure>

이런 펄스 트레인 전압을 그대로 부하로 전달할 수 없습니다.
일정한 전압을 출력하는 것이 목표이기 때문입니다.
따라서 고주파 성분 및 노이즈를 거르기 위해 저역 필터를 추가로 달아줍니다.

<figure style="text-align: center;">
  <img src="./PEFigure/lpf전압.png" alt="lpf전압" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 저주파 필터를 거친 전압 파형)
  </figcaption>
</figure>

필터를 통과한 전압은 거의 일정한 레벨로 출력됩니다.
전압 레벨은 스위치의 구동 시간과 관련되어 있습니다.
스위칭 주기 대비 스위치가 켜져 있는 시간의 비를 **듀티 비(Duty Ratio)**라고 합니다.
위 회로의 경우는 듀티 비가 클수록 전력이 전달되는 시간이 길어져서 전압 레벨이 높아집니다.
이런 원리로 전력 변환이 이루어집니다.

---

## 제어기

제어기를 통해 출력 전압을 제어해야 합니다.
제어기는 전압이나 전류의 정보를 가지고 피드백을 합니다.
보통 전압의 경우는 출력 전압이 이용되고, 전류의 경우는 인덕터 전류가 이용됩니다.
이렇게 전압 정보만을 이용한 제어 기법을 [전압 모드 제어](./ConverterVMC.md)라고 합니다.
전압 정보에 이어 전류 정보까지 이용한 제어 기법을 전류 모드 제어라고 합니다.
제어 변수가 많을수록 복잡도가 매우 커집니다.
제어기에 제어 변수들이 입력되면 내부 알고리즘에 따라 지령 값에 가까워지는 방향으로 신호를 출력합니다.
출력된 신호는 주로 듀티 비를 변화시키고, 주파수를 변화시키는 경우도 있습니다.

---

## 펄스 폭 변조

스위칭을 통해 전력 변환을 수행하려면 스위칭 신호를 공급해야 합니다.
즉, 시스템의 다른 부분에서 트랜지스터를 구동하는 신호를 받아야 합니다.
신호가 $$1$$이면 트랜지스터를 구동하고, $$0$$이면 구동하지 않는 방식으로 동작을 시킨다고 해봅시다.
이러한 신호를 생성하는 방법은 여러 가지가 있지만, 두 신호의 대소 비교를 통해 생성할 수 있습니다.
하나의 신호는 변하지 않는 기준 신호로 삼고, 또 다른 신호는 시스템의 현재 상태를 반영할 수 있는 방식으로 설계를 하는 것이 적절합니다.
전자의 신호는 외부에서 공급하고, 

---

## 컨버터

---

## 컨버터의 동작 모드

컨버터는 인덕터에 흐르는 전류에 따라 동작 모드가 나뉘게 됩니다.

### 인덕터 전류

컨버터에 있는 인덕터에는 보통 구간별로 일정한 전압이 걸립니다.
임의의 구간 $$[t_0,t]$$에서 인덕턴스가 $$L$$인 인덕터에 흐르는 전류는 다음과 같습니다.

$$
i_L(t)=\int_{t_0}^{t}\frac{v_L}{L}dt'+i_L(t_0)
$$

전압이 일정하므로 다음과 같이 쓸 수 있습니다.

$$
i_L(t)=\frac{v_L\left(t-t_0\right)}{L}
$$

일차함수의 형태입니다.
전압은 상황에 따라 다르므로 양수 또는 음수가 될 수 있습니다.
또한 인덕터 전류는 연속적이므로 다음과 같이 나타낼 수 있습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/인덕터전류임의.png" alt="인덕터전류임의" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 임의의 구간에 대한 인덕터 전류 파형)
  </figcaption>
</figure>

컨버터에 있는 다이오드로 인해 역전류가 차단되므로, 수식은 점선으로 표시하고, 실제 전류는 실선으로 표시했습니다.
스위칭 주파수가 일정하다면, 세 경우로 나눌 수 있습니다.

### CCM 동작

먼저 인덕터 전류가 항상 양수인 경우입니다.
인덕터에 항상 전류가 흐르는 경우로, **CCM(Continouos Conduction Mode) 동작** 또는 **연속 전도 모드 동작**이라고 합니다.

<figure style="text-align: center;">
  <img src="./PEFigure/CCM.png" alt="CCM" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. CCM에서의 인덕터 전류 파형)
  </figcaption>
</figure>

### DCM 동작

다음으로 인덕터 전류가 $$0$$이 되는 구간이 있는 경우입니다.
인덕터에 전류가 흐르지 않는 구간이 있는 경우로, **DCM(Discontinuous Conduction Mode)** 동작 또는 **불연속 전도 모드** 동작이라고 합니다.

<figure style="text-align: center;">
  <img src="./PEFigure/DCM.png" alt="DCM" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. DCM에서의 인덕터 전류 파형)
  </figcaption>
</figure>

### BCM 동작

다음으로 인덕터 전류가 $$0$$이 되는 순간이 있는 경우입니다.
인덕터에 전류가 흐르지 않는 구간이 있는 경우로, **BCM(Borderline(or Boundary) Conduction Mode)** 동작 또는 **경계 전도 모드 **동작이라고 합니다.
**CrCM(Critical Conduction Mode)** 동작이라고도 합니다.

<figure style="text-align: center;">
  <img src="./PEFigure/BCM.png" alt="BCM" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. BCM에서의 인덕터 전류 파형)
  </figcaption>
</figure>

### 버스트 모드

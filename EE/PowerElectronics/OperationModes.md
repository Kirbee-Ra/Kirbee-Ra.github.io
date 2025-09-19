컨버터의 동작 모드
=

---

## 목차

- [인덕터 전류](#인덕터-전류)
- [CCM 동작](#ccm-동작)
- [BCM 동작](#bcm-동작)
- [DCM 동작](#dcm-동작)
- [버스트 모드](#버스트-모드)

---

## 인덕터 전류

컨버터에 있는 인덕터에는 보통 구간별로 일정한 전압이 걸립니다.
임의의 구간 $$[t_0,t]$$에서 인덕턴스가 $$L$$인 인덕터에 흐르는 전류는 다음과 같습니다.

$$
i_L(t)=\int_{t_0}^{t}\frac{v_L}{L}dt'+i_L(t_1)
$$

전압이 일정하므로 다음과 같이 쓸 수 있습니다.

i_L(t)=\frac{v_L\left(t-t_0\right)}{L}

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

---

## CCM 동작

먼저 인덕터 전류가 항상 양수인 경우입니다.
인덕터에 항상 전류가 흐르는 경우로, **CCM(Continouos Conduction Mode) 동작** 또는 **연속 전도 모드 동작**이라고 합니다.

<figure style="text-align: center;">
  <img src="./PEFigure/CCM.png" alt="CCM" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. CCM에서의 인덕터 전류 파형)
  </figcaption>
</figure>

---

## BCM 동작

다음으로 인덕터 전류가 $$0$$이 되는 순간이 있는 경우입니다.







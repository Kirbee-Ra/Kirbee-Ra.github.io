컨버터의 기초
=

---

## 목차
- [DC-DC 전력 변환 장치](#dc-dc-전력-변환-장치)
- [파워 스테이지](#파워-스테이지)
- [펄스 폭 변조](#펄스-폭-변조)
- [DC-DC 변환의 가정](#dc-dc-변환의-가정)
- [제어기](#제어기)
- [컨버터의 동작](#컨버터의-동작)

---

## DC-DC 전력 변환 장치

DC-DC 전력 변환 장치의 구조는 다음과 같습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/컨버터.png" alt="컨버터" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. DC-DC 전력 변환 장치의 구조)
  </figcaption>
</figure>

입력을 받아서 전압 레벨을 변환한 뒤, 부하로 출력합니다.
여기서 전압 레벨을 변환하는 부분을 **파워 스테이지(Power Stage)**라고 합니다.
입력단에서 전압 변동 혹은 노이즈가 생길 수 있고, 부하가 순수한 저항성 부하가 아니거나 부하 변동이 생길 수 있습니다.
이러한 외란이 시스템에 입력돼도 출력 전압을 일정하게 유지할 수 있도록 제어기가 필요합니다.
파워 스테이지와 제어기를 통틀어 **컨버터(Converter)**라고 합니다.

---

## 파워 스테이지

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

## 펄스 폭 변조



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

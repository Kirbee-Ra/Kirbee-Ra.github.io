전력 MOSFET
=

---

## 목차
- [전력 MOSFET](#power-mosfet)
- [스위칭](#스위칭)

---

<h2 id="power-mosfet">전력 MOSFET</h2>

### 전력 MOSFET의 구조

---

## 스위칭

이제 전력 MOSFET의 스위칭에 대해 설명하겠습니다.
다음과 같이 스위칭 파워-폴에 연결된 MOSFET을 생각해봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/전력 MOSFET 스위칭 파워 폴.png" alt="전력 MOSFET 스위칭 파워 폴" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 전력 MOSFET이 연결된 스위칭 파워-폴)
  </figcaption>
</figure>

우선, MOSFET은 게이트에 전압을 인가하여 구동해야 합니다.
게이트 전압과 드레인 전류는 다음의 관계가 있습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/MOSFET VG_ID.png" alt="MOSFET VG_ID" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. MOSFET의 게이트 전압과 드레인 전류의 관계)
  </figcaption>
</figure>

문턱 값$$\left(V_{GS(TH)}\right)$$을 넘어야 채널이 형성되어 전류가 흐를 수 있습니다.
게이트 전압을 인가하여 문턱 값에 도달하는 시간을 턴 온 지연 시간$$t_{d(on)}$$이라고 합시다.
이때 MOSFET에 걸리는 전압(드레인-소스 전압)과 흐르는 전류는 다음과 같습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/MOSFET VI 1.png" alt="MOSFET VI 1" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 턴-온 지연 시간에서의 MOSFET 전압 및 전류)
  </figcaption>
</figure>


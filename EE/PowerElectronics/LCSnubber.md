LC 스너버
=

---

## 목차

---

## LC 스너버

LC 스너버는 무손실 스너버(Lossless Snubber)의 일종입니다.
말 그대로 이론적으로 손실 없이 전압을 클램핑합니다.
LC 스너버를 적용한 플라이백 컨버터는 그림과 같습니다.

<figure style="text-align: center;">
  <img src="./PEFigure/LC스너버.png" alt="LC스너버" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. LC 스너버를 적용한 플라이백 컨버터)
  </figcaption>
</figure>

누설 인덕터에 저장된 에너지가 스너버 커패시터와 스너버 인덕터를 거쳐 다시 입력단으로 되돌아갑니다.

---

## 동작 원리

먼저 스위치가 턴-오프 상태일 때부터 살펴봅시다.

<figure style="text-align: center;">
  <img src="./PEFigure/LCph1.png" alt="LCph1" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 턴-오프 상태)
  </figcaption>
</figure>

이전 사이클에 의해 스너버 커패시터는 충전된 상태입니다.

<!-- 두 이미지를 감싸는 행 컨테이너 -->
<div style="display: flex; justify-content: center; gap: 1rem; flex-wrap: wrap;">

  <!-- 첫 번째 이미지 -->
  <figure style="text-align: center; flex: 1 1 45%;">
    <img src="./PEFigure/CSN.png" alt="LCph1" style="width: 42%;" />
    <figcaption style="margin-top: 8px; font-size: 0.9em; color: #555;">
      (그림 1. 턴-오프 상태)
    </figcaption>
  </figure>

  <!-- 두 번째 이미지 -->
  <figure style="text-align: center; flex: 1 1 45%;">
    <img src="./PEFigure/3P2Z.png" alt="LCph2" style="width: 42%;" />
    <figcaption style="margin-top: 8px; font-size: 0.9em; color: #555;">
      (그림 2. 턴-온 상태)
    </figcaption>
  </figure>

</div>


---

## 스너버 설계 고려 사항

### 스너버 커패시턴스

### 스너버 인덕턴스

### 다이오드 역 회복 특성

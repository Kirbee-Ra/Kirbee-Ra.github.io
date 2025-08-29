# 전력전자

---

## 전력전자

---

## 기초

전력전자를 공부하기 위한 기초 지식을 다룹니다.
- [전력 반도체]
- [전력 다이오드](./PowerDiode.md)
- [BJT]
- [전력 MOSFET](./PowerMOSFET.md)
- [IGBT]
- [축전기]
- [인덕터](../CircuitTheory/Inductor.md)
- [변압기]
- [전력 변환 회로](./PowerConversionCircuit.md)
- [컨버터의 기초](./ConverterBasic.md)

---

## DC-DC 변환: 컨버터

### 비절연형 컨버터

입력단과 출력단이 전기적으로 연결된 컨버터입니다.
- [벅 컨버터](./BuckConverter.md)
- [부스트 컨버터]
- [벅-부스트 컨버터]
- [세픽]
- [척 컨버터]

### 절연형 컨버터

입력단과 출력단이 전기적으로 절연된 컨버터입니다.
- [플라이백 컨버터]
- [포워드 컨버터]
- [풀-브릿지 컨버터]
- [하프-브릿지 컨버터]
- [푸쉬-풀 컨버터]
- [DAB 컨버터]

### 공진형 컨버터

공진 현상을 이용한 컨버터입니다.
- [공진 스위치]
- [LLC 공진형 컨버터]
- [준-공진형 컨버터]

### LTI 시스템 구축

선형 제어론을 이용한 제어기 설계를 위해 컨버터를 LTI 시스템으로 바꾸는 방법입니다.
- [컨버터 모델링](./ConverterModeling.md)
- [컨버터의 평균화 모델](./AveragedModel.md)
- [컨버터의 소신호 모델](./ConverterSmallSignalModel.md)
- [파워 스테이지의 전달 함수](./ConverterTransferFunction.md)

### 컨버터 제어

컨버터를 제어하는 방법입니다.
- [컨버터의 성능](./ConverterDynamics.md)
- [컨버터의 전압 모드 제어](./ConverterVMC.md)
- [컨버터의 전류 모드 제어](./ConverterCMC.md)
- [추가 요소 정리](./EET.md)

### 스너버 회로

소자에 가해지는 전압 스트레스를 줄이는 방법입니다.
- [RC 스너버]
- [RCD 클램프]
- [능동 클램프]
- [LC 스너버](./LCSnubber.md)

### 컨버터의 효율 개선

컨버터의 효율을 개선하는 방법입니다.
- [동기 정류](./SynchronousRectification.md)
- [소프트 스위칭]

---

## AC-DC 변환: 정류기
- [정류 회로]
- [역률 개선 회로]

---

## DC-AC 변환: 인버터
- [인버터]

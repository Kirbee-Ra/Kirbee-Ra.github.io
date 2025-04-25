하프 브릿지 컨버터
=

---

## 목차

---

## 비대칭 하프 브릿지 컨버터

**비대칭 하프 브릿지 컨버터(Asymmetrical Half-Bridge Converter)**는 두 스위치가 상보적으로 동작하는 하프 브릿지 컨버터입니다.

### 회로도

### 동작 방식

### 평균화 모델

컨버터의 제어기를 설계하기에 앞서 LTI 시스템으로 바꿔야 합니다.
먼저 회로 평균화를 해봅시다.
두 스위치는 상보적으로 동작합니다.
그러므로 이를 다음과 같은 SPDT 스위치로 모델링할 수 있습니다.

(comp switch)

각 변수의 관계식은 다음과 같습니다.

$$
\begin{cases}
	v_{cg}(t)=v_s(t)q(t)\\
i_a(t)=\left(i_m(t)+\displaystyle\frac{i_L(t)}{n}\right)q(t)
\end{cases}
$$

평균화하면 다음과 같습니다.

$$
\begin{cases}
	\overline{v}_{cg}(t)=\overline{v}_s(t)d(t)\\
	\overline{i}_a(t)=\left(\overline{i}_m(t)+\displaystyle\frac{\overline{i}_L(t)}{n}\right)d(t)
\end{cases}
$$

그러므로 이 스위치는 다음과 같이 모델링할 수 있습니다.

(dep source sw)

다음으로 

### 소신호 모델

### 개루프 입력-출력 전달 함수

### 개루프 듀티 비-출력 전달 함수

### 개루프 출력 임피던스 전달 함수

### 3P2Z 보상기 설계

### 음파 민감도

### 출력 임피던스

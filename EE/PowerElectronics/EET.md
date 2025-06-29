추가 요소 정리
= 

---

## 목차

- 비결합 컨버터
- 결합 컨버터
- 추가 요소 정리
- 입력단 임피던스를 고려한 폐루프 전달 함수
- 출력단 임피던스를 고려한 폐루프 전달 함수
- 루프 이득

---

## 비결합 컨버터

**비결합 컨버터(Uncoupled Converter)**란 이상적인 파워 스테이지와 제어기로만 구성된 컨버터입니다.
즉, 전원단 임피던스가 없고, 부하 또한 저항성인 상태입니다.

---

## 결합 컨버터

**결합 컨버터(Coupled Converter)**란 비결합 컨버터에 전원단 임피던스나 리액턴스성 부하 등의 다른 소자가 연결된 컨버터입니다.

---

## 추가 요소 정리

**추가 요소 정리(Extra Element Theorem, EET)**는 비결합 컨버터에 어떤 소자(추가 요소) 등이 결합된 경우, 전달 함수가 어떻게 변하는지를 나타내는 정리입니다.
즉, 비결합 컨버터와 결합 컨버터의 관계를 나타내는 정리입니다.
이 정리는 컨버터에 국한되지 않고, 일반적인 회로에 추가 요소가 결합된 경우에도 이용할 수 있습니다.
추가 요소가 컨버터에 직렬로 연결되는 경우와 병렬로 연결되는 경우로 나눌 수 있습니다.
추가 요소 정리를 살펴보기 전에 필요한 개념을 먼저 설명하겠습니다.

### 구동점 임피던스

먼저 추가 요소를 전류 $$I$$를 흐르게 하는 시험 전원으로 치환합니다.
이때, **구동점 임피던스(Driving Point Impedance)**는 입력이 $$0$$인 경우, 시험 전원의 임피던스를 의미합니다.

### 영 구동점 임피던스

**영 구동점 임피던스(Null Driving Point Impedance)**는 출력이 $$0$$인 경우, 시험 전원의 임피던스를 의미합니다.

### 병렬 추가 요소에 대한 정리

먼저 추가 요소가 병렬로 연결되는 경우를 살펴봅시다.
이 경우는 추가 요소가 개방되어야 비결합 컨버터가 됩니다.
이때 추가 요소 정리는 다음과 같이 나타납니다.

$$
H(s)=H_{oc}(s)\frac{1+\displaystyle\frac{Z_n(s)}{Z(s)}}{1+\displaystyle\frac{Z_d(s)}{Z(s)}}
$$

여기서 $$H_{oc}(s)$$는 비결합 컨버터(추가 요소가 개방된 개방 회로)의 전달 함수, $$Z_d(s)$$는 구동점 임피던스, $$Z_n(s)$$는 영 구동점 임피던스, $$Z(s)$$는 추가 요소의 임피던스입니다.

### 증명

다음과 같이 회로의 출력과 추가 요소 양단의 전압을 회로의 입력과 추가 요소에 흐르는 전류로 표현하는 4단자망 방정식을 생각해봅시다.

$$
\begin{align*}
\begin{bmatrix}
u_o\\
V
\end{bmatrix}=\begin{bmatrix}
a_{11}&a_{12}\\
a_{21}&a_{22}
\end{bmatrix}\begin{bmatrix}
u_i\\
I
\end{bmatrix}
\end{align*}
$$

그리고 추가 요소에 걸린 전압과 흐르는 전류는 전압 극성에 의해 다음과 같이 나타납니다.

$$
V=-IZ
$$

먼저 추가 요소에 전류가 흐르지 않는다고 해봅시다.
즉, 추가 요소가 개방된 상태입니다.
이때 성분 $$a_{11}$$은 다음과 같이 나타납니다.

$$
a_{11}=\frac{u_o}{u_i}\bigg\vert_{I=0}
$$

추가 요소가 개방된 상태에서의 회로의 입력과 출력의 비이므로 이는 개방 회로의 전달 함수 $$H_{oc}(s)$$를 나타냅니다.
다음으로 입력이 $$0$$인 경우를 생각해봅시다.
이때 성분 $$a_{22}$$는 다음과 같습니다.

$$
a_{22}=\frac{V}{I}\bigg\vert_{u_i=0}
$$

입력이 $$0$$일 때 추가 요소에 걸린 전압과 흐르는 전류의 비이므로 이는 구동점 임피던스 $$Z_d(s)$$를 나타냅니다.



### 직렬 추가 요소에 대한 정리

병렬 추가 요소에 대한 정리를 다시 살펴봅시다.

$$
H(s)=H_{oc}(s)\frac{1+\displaystyle\frac{Z_n(s)}{Z(s)}}{1+\displaystyle\frac{Z_d(s)}{Z(s)}}
$$

이 식의 분모와 분자에 각각 $$Z(s)$$를 곱한 뒤, 분배 법칙을 통해 분모와 분자를 각각 $$Z_d(s)$$와 $$Z_n(s)$$으로 묶으면 다음과 같습니다.

$$
H(s)=H_{oc}(s)\frac{Z_n(s)}{Z_d(s)}\frac{1+\displaystyle\frac{Z(s)}{Z_n(s)}}{1+\displaystyle\frac{Z(s)}{Z_d(s)}}
$$

추가 요소가 직렬로 연결된 경우 $$Z(s)=0$$일 때, $$H(s)$$는 비결합 컨버터(추가 요소가 단락된 단락 회로)의 전달 함수입니다.
이를 다음과 같이 씁시다.

$$
H_{sc}(s)=H_(s)\vert_{Z(s)=0}=H_{oc}(s)\frac{Z_n(s)}{Z_d(s)}
$$

따라서 직렬 추가 요소에 대한 정리는 다음과 같습니다.

$$
H(s)=H_{sc}(s)\frac{1+\displaystyle\frac{Z(s)}{Z_n(s)}}{1+\displaystyle\frac{Z(s)}{Z_d(s)}}
$$


### 확장된 추가 요소 정리

---



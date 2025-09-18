파워 스테이지의 전달 함수
=

---

## 목차

- [컨버터의 구성](#컨버터의-구성)
- [벅 컨버터](#벅-컨버터)
- [부스트 컨버터](#부스트-컨버터)
- [벅-부스트 컨버터](#벅-부스트-컨버터)
- [플라이백 컨버터](#플라이백-컨버터)

---

## 주파수 응답

시스템을 분석할 때, 입력 변동에 대해 출력이 어떻게 변하는지 관측합니다.
입력은 다양한 주파수 성분을 지니고 있습니다.
따라서 주파수 영역에서 분석을 하면, 특정 주파수에서 출력이 어떻게 변하는지 알 수 있습니다.

### 전달 함수

주파수 영역에서 캐스케이딩은 두 함수의 곱으로 나타낼 수 있으므로 출력을 다음과 같이 쓸 수 있습니다.

$$
x_o(s)=T(s)x_{in}(s)
$$

여기서 입력 변동에 대한 출력 변동의 비를 **전달 함수(Transfer Function)**라고 합니다.

$$
T(s)=\frac{x_o(s)}{x_{in}(s)}
$$

주파수 영역에서만 비로 정의됩니다.

### 주파수 응답 분석

주파수 응답을 분석하기 위해 다음과 같이 $$s=j\omega$$를 대입합시다.

$$
T(j\omega)=\frac{x_o(j\omega)}{x_{in}(j\omega)}
$$

이 전달 함수의 크기와 위상을 분석하면 주파수 응답을 알 수 있습니다.

$$
\begin{cases}
	\left\vert T(j\omega)\right\vert=\displaystyle\frac{x_o(j\omega)}{x_{in}(j\omega)}\\
	\angle T(j\omega)=\angle x_{o}(j\omega)-\angle x_{in}(j\omega)
\end{cases}
$$

---

## 컨버터의 구성

다음은 컨버터의 블록 다이어그램입니다.

<figure style="text-align: center;">
  <img src="./PEFigure/컨버터bd.png" alt="컨버터bd" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 컨버터의 블록 다이어그램)
  </figcaption>
</figure>

컨버터를 분석하기 위해 각 부분의 개루프 전달 함수를 알아야 합니다.
$$F_m,-F_v$$는 [컨버터의 소신호 모델](./ConverterSmallSignalModel.md)에서 다뤘습니다.
이제 구해야 하는 전달 함수는 다음과 같습니다.
1. 개루프 입력-출력 전달 함수 $$G_{vs}(s)=\displaystyle\frac{\hat{v}_o(s)}{\hat{v}_{in}(s)}$$
2. 개루프 듀티 비-출력 전달 함수 $$G_{vd}(s)=\displaystyle\frac{\hat{v}_o(s)}{\hat{d}(s)}$$
3. 개루프 출력 임피던스 전달 함수 $$Z_p(s)=\displaystyle\frac{\hat{v}_o(s)}{\hat{i}_o(s)}$$
   
이 전달 함수들을 모두 구하면 컨버터의 전달 함수를 구하여 제어기를 설계할 수 있습니다.

### 개루프 전달 함수

전달 함수는 기본적으로 하나의 변수가 변할 때, 우리가 관심을 갖는 변수가 어떻게 변하는지를 나타냅니다.
그러므로 두 변수를 제외하고 다른 변수의 변화는 없다고 가정합니다.
이렇게 가정을 하고 나면 회로가 더 간단해집니다.
적당한 지점에 대해 KVL, KCL 등의 회로 법칙을 적용하여 원하는 개루프 전달 함수를 구할 수 있습니다.
이때, 기생 저항들을 모두 고려해야 합니다.
뒤에 나오지만 기생 저항에 의한 항이 동작에 영향을 미치기 때문입니다.
단, 이 기생 저항들은 부하 저항에 비해 매우 작은 값을 가집니다.

$$
R_l,R_c\ll R
$$

---

## 벅 컨버터

벅 파워 스테이지의 소신호 모델은 다음과 같습니다.

### 벅 컨버터의 $$G_{vs}(s)$$

우리가 관심을 갖는 변수는 $$\hat{v}_{in},\hat{v}_o$$입니다.
따라서 다음과 같이 다른 변수의 변화는 $$0$$으로 가정합니다.

$$
\hat{d}(s)=\hat{i}_o(s)=0
$$

이 조건 하에 회로가 다음과 같이 바뀝니다.

<figure style="text-align: center;">
  <img src="./PEFigure/벅Gvs.png" alt="벅Gvs" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 입력 전압 변동을 고려한 벅 파워 스테이지)
  </figcaption>
</figure>

변압기의 2차 측에 전압 $$D\hat{v}_{in}(s)$$가 걸립니다.
전압 분배를 이용하면 다음과 같습니다.

기생 저항들은 부하 저항에 비해 매우 작으므로 다음과 같이 근사할 수 있습니다.

따라서 벅 컨버터의 개루프 입력-출력 전달 함수는 다음과 같습니다.

$$
G_{vs}(s)=D\frac{1+\displaystyle\frac{s}{\omega_{esr}}}{1+\displaystyle\frac{s}{Q\omega_0}+\displaystyle\frac{s^2}{\omega_0^2}}
$$

### 벅 컨버터의 $$G_{vd}(s)$$

우리가 관심을 갖는 변수는 $$\hat{d},\hat{v}_o$$입니다.
따라서 다음과 같이 다른 변수의 변화는 $$0$$으로 가정합니다.

$$
\hat{v}_{in}(s)=\hat{i}_o(s)=0
$$

이 조건 하에 회로가 다음과 같이 바뀝니다.

<figure style="text-align: center;">
  <img src="./PEFigure/벅Gvd.png" alt="벅Gvd" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 듀티 비 변동을 고려한 벅 파워 스테이지)
  </figcaption>
</figure>

변압기의 2차 측에 전압 $$V_{in}\hat{d}(s)$$가 걸립니다.
전압 분배를 이용하면 다음과 같습니다.

기생 저항들은 부하 저항에 비해 매우 작으므로 다음과 같이 근사할 수 있습니다.

따라서 벅 컨버터의 개루프 듀티 비-출력 전달 함수는 다음과 같습니다.

$$
G_{vd}(s)=V_{in}\frac{1+\displaystyle\frac{s}{\omega_{esr}}}{1+\displaystyle\frac{s}{Q\omega_0}+\displaystyle\frac{s^2}{\omega_0^2}}
$$

### 벅 컨버터의 $$Z_p(s)$$

우리가 관심을 갖는 변수는 $$\hat{i}_o,\hat{v}_o$$입니다.
따라서 다음과 같이 다른 변수의 변화는 $$0$$으로 가정합니다.

$$
\hat{v}_{in}(s)=\hat{d}(s)=0
$$

이 조건 하에 회로가 다음과 같이 바뀝니다.

<figure style="text-align: center;">
  <img src="./PEFigure/벅Zp.png" alt="벅Zp" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 부하 변동을 고려한 벅 파워 스테이지)
  </figcaption>
</figure>

변압기의 2차 측이 단락되었습니다.
변압기의 2차 측과 출력단을 거치는 폐회로를 따라 KVL을 적용하면 다음과 같습니다.

기생 저항들은 부하 저항에 비해 매우 작으므로 다음과 같이 근사할 수 있습니다.

따라서 벅 컨버터의 개루프 출력 임피던스 전달 함수는 다음과 같습니다.

$$
Z_p(s)=R_l\frac{\left(1+\displaystyle\frac{s}{\omega_z}\right)\left(1+\displaystyle\frac{s}{\omega_{esr}}\right)}{1+\displaystyle\frac{s}{Q\omega_0}+\displaystyle\frac{s^2}{\omega_0^2}}
$$

---

## 부스트 컨버터

부스트 파워 스테이지의 소신호 모델은 다음과 같습니다.

### 부스트 컨버터의 $$G_{vs}(s)$$

우리가 관심을 갖는 변수는 $$\hat{v}_{in},\hat{v}_o$$입니다.
따라서 다음과 같이 다른 변수의 변화는 $$0$$으로 가정합니다.

$$
\hat{v}_{in}(s)=\hat{i}_o(s)=0
$$

이 조건 하에 회로가 다음과 같이 바뀝니다.

<figure style="text-align: center;">
  <img src="./PEFigure/벅Gvs.png" alt="벅Gvs" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 입력 전압 변동을 고려한 부스트트 파워 스테이지)
  </figcaption>
</figure>

이제 다음과 같이 입력단과 변압기를 거치는 폐회로를 따라 KVL을 적용하고, 출력단에 KCL을 적용하면 다음과 같습니다.

기생 저항들은 부하 저항에 비해 매우 작으므로 다음과 같이 근사할 수 있습니다.

따라서 부스트 컨버터의 개루프 입력-출력 전달 함수는 다음과 같습니다.

$$
G_{vs}(s)=\frac{1}{D'}\frac{1+\displaystyle\frac{s}{\omega_{esr}}}{1+\displaystyle\frac{s}{Q\omega_0}+\displaystyle\frac{s^2}{\omega_0^2}}
$$

벅 컨버터의 경우와는 다르게 공진 주파수와 Q 인자가 듀티 비에 의존하는 형태로 나옵니다.
이는 인덕터가 출력단 축전기와 직접적으로 연결되어 있지 않고, PWM 스위치에 의해 분리되어 있어서 그렇습니다.
벅 컨버터는 스위치의 연결 상태와 관계 없이 출력에 인덕터가 직접 관여했습니다.
하지만 부스트 컨버터는 스위치가 꺼진 상태에만 출력에 인덕터가 관여합니다.
따라서 $$D'=1-D$$의 제곱으로 나눠진 유효 인덕턴스로 계산됩니다.
전력 전달 관점에서 볼 때, 이상 변압기에서 유효 임피던스는 턴 비의 제곱이 곱해지거나 나눠집니다.
이와 동일하게 해석하면 됩니다.
따라서 부스트 컨버터의 입력-출력 동 특성은 동작점에 의존하는 것을 알 수 있습니다.

### 부스트 컨버터의 $$G_{vd}(s)$$

우리가 관심을 갖는 변수는 $$\hat{d},\hat{v}_o$$입니다.
따라서 다음과 같이 다른 변수의 변화는 $$0$$으로 가정합니다.

$$
\hat{d}(s)=\hat{i}_o(s)=0
$$

이 조건 하에 회로가 다음과 같이 바뀝니다.

<figure style="text-align: center;">
  <img src="./PEFigure/벅Gvd.png" alt="벅Gvd" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 듀티 비 변동을 고려한 부스트 파워 스테이지)
  </figcaption>
</figure>

이제 다음과 같이 입력단과 출력단을 거치는 폐회로를 따라 KVL을 적용하고, 출력단에 KCL을 적용하면 다음과 같습니다.

기생 저항들은 부하 저항에 비해 매우 작으므로 다음과 같이 근사할 수 있습니다.

따라서 부스트 컨버터의 개루프 듀티 비-출력 전달 함수는 다음과 같습니다.

$$
G_{vd}(s)=\frac{V_{in}}{D'^2}\frac{\left(1-\displaystyle\frac{s}{\omega_{rhp}}\right)\left(1+\displaystyle\frac{s}{\omega_{esr}}\right)}{1+\displaystyle\frac{s}{Q\omega_0}+\displaystyle\frac{s^2}{\omega_0^2}}
$$

전달 함수를 보면 분자에 우반면 영점이 포함되어 있습니다.
이 영점은 동작점에 의존합니다.
따라서 동작점이 변하면 이 영점 또한 변하므로 **이동 우반면 영점(Moving RHP Zero)**이라고 합니다.
이 영점은 일반적으로 esr 영점보다 낮은 값입니다.
분모에는 이중 극점이 존재하므로 전달 함수의 위상이 $$-180^{\circ}$$보다 낮아지는 구간이 생깁니다.
이런 시스템을 **비 최소 위상 시스템(Non-Minimum Phase System)**이라고 합니다.
이런 시스템은 우반면 영점으로 인해 제어기 설계 난이도가 상승합니다.
듀티 비를 높이면 조금 완회될 수는 있으나 의미가 있지는 않습니다.
자세한 내용은 [컨버터의 전압 모드 제어](./ConverterVMC) 문서를 참고 바랍니다.

### 부스트 컨버터의 $$Z_p(s)$$

우리가 관심을 갖는 변수는 $$\hat{i}_o,\hat{v}_o$$입니다.
따라서 다음과 같이 다른 변수의 변화는 $$0$$으로 가정합니다.

$$
\hat{v}_{in}(s)=\hat{d}(s)=0
$$

이 조건 하에 회로가 다음과 같이 바뀝니다.

<figure style="text-align: center;">
  <img src="./PEFigure/벅Zp.png" alt="벅Zp" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 부하 변동을 고려한 부스트트 파워 스테이지)
  </figcaption>
</figure>

이제 다음과 같이 입력단과 출력단을 거치는 폐회로를 따라 KVL을 적용하고, 출력단에 KCL을 적용하면 다음과 같습니다.

기생 저항들은 부하 저항에 비해 매우 작으므로 다음과 같이 근사할 수 있습니다.

따라서 부스트 컨버터의 개루프 출력 임피던스 전달 함수는 다음과 같습니다.

$$
Z_p(s)=\frac{R_l}{D'^2}\frac{\left(1+\displaystyle\frac{s}{\omega_z}\right)\left(1+\displaystyle\frac{s}{\omega_{esr}}\right)}{1+\displaystyle\frac{s}{Q\omega_0}+\displaystyle\frac{s^2}{\omega_0^2}}
$$


---

## 벅-부스트 컨버터

벅-부스트 파워 스테이지의 소신호 모델은 다음과 같습니다.

### 벅-부스트 컨버터의 $$G_{vs}(s)$$

우리가 관심을 갖는 변수는 $$\hat{v}_{in},\hat{v}_o$$입니다.
따라서 다음과 같이 다른 변수의 변화는 $$0$$으로 가정합니다.

$$
\hat{d}(s)=\hat{i}_o(s)=0
$$

이 조건 하에 회로가 다음과 같이 바뀝니다.

<figure style="text-align: center;">
  <img src="./PEFigure/벅Gvs.png" alt="벅Gvs" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 입력 전압 변동을 고려한 벅-부스트트 파워 스테이지)
  </figcaption>
</figure>

이제 다음과 같이 출력단과 변압기를 거치는 폐회로를 따라 KVL을 적용하고, 출력단에 KCL을 적용하면 다음과 같습니다.

기생 저항들은 부하 저항에 비해 매우 작으므로 다음과 같이 근사할 수 있습니다.

따라서 부스트 컨버터의 개루프 입력-출력 전달 함수는 다음과 같습니다.

$$
G_{vs}(s)=\frac{D}{D'}\frac{1+\displaystyle\frac{s}{\omega_{esr}}}{1+\displaystyle\frac{s}{Q\omega_0}+\displaystyle\frac{s^2}{\omega_0^2}}
$$

### 벅-부스트 컨버터의 $$G_{vd}(s)$$

우리가 관심을 갖는 변수는 $$\hat{d},\hat{v}_o$$입니다.
따라서 다음과 같이 다른 변수의 변화는 $$0$$으로 가정합니다.

$$
\hat{d}(s)=\hat{i}_o(s)=0
$$

이 조건 하에 회로가 다음과 같이 바뀝니다.

<figure style="text-align: center;">
  <img src="./PEFigure/벅Gvd.png" alt="벅Gvd" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 듀티 비 변동을 고려한 벅-부스트 파워 스테이지)
  </figcaption>
</figure>

이제 다음과 같이 변압기와 출력단을 거치는 폐회로를 따라 KVL을 적용하고, 출력단에 KCL을 적용하면 다음과 같습니다.

기생 저항들은 부하 저항에 비해 매우 작으므로 다음과 같이 근사할 수 있습니다.

따라서 벅-부스트 컨버터의 개루프 듀티 비-출력 전달 함수는 다음과 같습니다.

$$
G_{vd}(s)=\frac{V_{in}}{D'^2}\frac{\left(1-\displaystyle\frac{s}{\omega_{rhp}}\right)\left(1+\displaystyle\frac{s}{\omega_{esr}}\right)}{1+\displaystyle\frac{s}{Q\omega_0}+\displaystyle\frac{s^2}{\omega_0^2}}
$$

### 벅-부스트 컨버터의 $$Z_p(s)$$

우리가 관심을 갖는 변수는 $$\hat{i}_o,\hat{v}_o$$입니다.
따라서 다음과 같이 다른 변수의 변화는 $$0$$으로 가정합니다.

$$
\hat{v}_{in}(s)=\hat{d}(s)=0
$$

이 조건 하에 회로가 다음과 같이 바뀝니다.

<figure style="text-align: center;">
  <img src="./PEFigure/벅Zp.png" alt="벅Zp" width="100%"/>
  <figcaption style="text-align: center; margin-top: 8px; font-size: 0.9em; color: #555;">
    (그림. 부하 변동을 고려한 벅-부스트 파워 스테이지)
  </figcaption>
</figure>

이제 다음과 같이 변압기와 출력단을 거치는 폐회로를 따라 KVL을 적용하고, 출력단에 KCL을 적용하면 다음과 같습니다.

기생 저항들은 부하 저항에 비해 매우 작으므로 다음과 같이 근사할 수 있습니다.

따라서 벅-부스트 컨버터의 개루프 출력 임피던스 전달 함수는 다음과 같습니다.

$$
Z_p(s)=\frac{R_l}{D'^2}\frac{\left(1+\displaystyle\frac{s}{\omega_z}\right)\left(1+\displaystyle\frac{s}{\omega_{esr}}\right)}{1+\displaystyle\frac{s}{Q\omega_0}+\displaystyle\frac{s^2}{\omega_0^2}}
$$

---

## 실험을 통한 개루프 듀티 비-출력 전달 함수 분석

개루프 듀티 비-출력 전달 함수를 실험적으로 알아내려면 다음과 같이 실험을 세팅해야 합니다.

듀티 비에 변화를 주려면 PWM 블록에 입력되는 제어 전압이 변화를 줘야합니다.
또 이 제어 전압을 변화시키려면 연산 증폭기의 단자에 소신호를 입력해야 합니다.
소신호가 입력되면 제어 전압은 다음과 같이 dc항과 소신호 항으로 나타낼 수 있습니다.

$$
v_{ctrl}=V_{dc}+\hat{v}_p
$$

그리고 듀티 비는 다음과 같이 나타낼 수 있습니다.

$$
d(t)=D+\hat{d}(t)
$$

소신호 $$\hat{v}_p$$에 대한 출력 전압의 변동은 다음과 같습니다.

$$
\frac{\hat{v}_o(s)}{\hat{v}_p(s)}=\frac{\hat{d}(s)}{\hat{v}_p(s)}\frac{\hat{v}_o(s)}{\hat{d}(s)}
$$

제어 전압의 변동에 대한 듀티 비의 변화가 바로 PWM 블록의 전달 함수입니다.

$$
\frac{\hat{d}(s)}{\hat{v}_p(s)}=F_m
$$

따라서 다음과 같습니다.

$$
\frac{\hat{v}_o(s)}{\hat{v}_p(s)}=F_m\frac{\hat{v}_o(s)}{\hat{d}(s)}
$$

그러므로 개루프 듀티 비-출력 전달 함수는 다음과 같습니다.

$$
	\begin{align*}
\frac{\hat{v}_o(s)}{\hat{d}(s)}=\frac{1}{F_m}\frac{\hat{v}_o(s)}{\hat{v}_p(s)}
	\end{align*}
$$

따라서 연산 증폭기의 입력측 단자에 소신호를 가했을 때, 출력 전압 변동에 대해 분석한다면, 개루프 듀티 비-출력 전달 함수를 구할 수 있습니다.

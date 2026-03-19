공진형 컨버터
=

---

## 목차

---

## LLC 공진형 컨버터

### 동작 모드

초기 상태

$$
\begin{align*}
&i_{Lr}(0)=I_{Lr0},\\
&v_{Cr}(0)=V_{Cr0},\\
&i_m(0)=I_{m0},\\
&v_m(0)=nV_o
\end{align*}
$$

공진 주파수

$$
\omega_r=\sqrt{L_rC_r}
$$

모드 1

공진 인덕터 전류

$$
i_{Lr}(t)=I_{Lr0}\cos\left(\omega_rt\right)+\left(V_{in}-nV_o-V_{Cr0}\right)\sqrt{\frac{C_r}{L_r}}\sin\left(\omega_rt\right)
$$

공진 커패시터 전압

$$
v_{Cr}(t)=V_{in}-nV_o+I_{Lr0}\sqrt{\frac{L_r}{C_r}}\sin\left(\omega_rt\right)-\left(V_{in}-nV_o-V_{Cr0}\right)\cos\left(\omega_rt\right)
$$

자화 전류

$$
i_m(t)=\frac{nV_o}{L_m}t+I_{m0}
$$

모드 2

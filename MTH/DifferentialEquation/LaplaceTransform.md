# 라플라스 변환

---

## 적분 변환

적분 변환(Integral Transform)은 어떤 함수를 다른 함수와 곱한 뒤, 적분을 통해 다른 변수를 갖도록 변환하는 방법입니다.
여기서 곱해지는 다른 함수를 핵(Kernel)이라고 하고, 핵은 원래 함수의 변수와 변환된 함수의 변수를 모두 갖고 있습니다.

$$
\begin{align*}
F(s)&=T\left[f(t)\right]\\
&=\int_{\alpha}^{\beta}f(t)K(s,t)dt
\end{align*}
$$

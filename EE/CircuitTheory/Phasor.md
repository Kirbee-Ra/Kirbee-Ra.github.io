# 위상자

---

## 오일러 공식

삼각 함수끼리의 연산은 비교적 복잡합니다. 지수 함수로 바꿀 수 있다면 연산이 더 편리해집니다. 이는 오일러 공식(Euler's Formula)을 이용하면 됩니다. 오일러 공식은 지수 함수와 삼각 함수 사이의 관계식을 나타냅니다.

$$
e^{jx}=\cos x+j\sin x
$$

### 유도

$$e^x$$의 테일러 전개는 다음과 같습니다.

$$
e^x=\sum_{k=0}^{\infty}\frac{x^k}{k!}
$$

이 식에서 $$x$$ 대신 $$jx를 대입하면 다음과 같습니다.

$$
\begin{align*}
		e^{j x}&=\sum_{k=0}^{\infty}\frac{\left(j x\right)^k}{k!}\\
		&=\frac{1}{0!}+\frac{jx}{1!}+\frac{-x^2}{2!}+\frac{-jx^3}{3!}+\frac{x^4}{4!}+\frac{jx^5}{5!}\cdots\\
		&=\left(\frac{1}{0!}+\frac{-x^2}{2!}+\frac{x^4}{4!}+\cdots\right)+\left(\frac{jx}{1!}+\frac{-jx^3}{3!}+\frac{jx^5}{5!}+\cdots\right)\\
		&=\left(\frac{1}{0!}+\frac{-x^2}{2!}+\frac{x^4}{4!}+\cdots\right)+j\left(\frac{x}{1!}+\frac{-x^3}{3!}+\frac{x^5}{5!}+\cdots\right)\\
		&=\sum_{k=0}^{\infty}\frac{\left(-1\right)^k x^{2k}}{\left(2k\right)!}+j\sum_{k=0}^{\infty}\frac{\left(-1\right)^k x^{2k+1}}{\left(2k+1\right)!}\\
		&=\cos x+j\sin x\\
	\end{align*}
 $$

 $$
 \begin{align*}
 \rightarrow e^{jx}=\cos x+j\sin x
 \end{align*}
 $$

 ---


 ## 위상자 변환


 앞서 살펴본 오일러 공식에서 $$e^{jx}$$의 실수 부분과 허수 부분은 다음과 같습니다.

 $$
\begin{align*}
		&\text{Re}\left[e^{jx}\right]=\cos x\\
		&\text{Im}\left[e^{jx}\right]=\sin x
	\end{align*}
 $$

 여기서 우리는 한 가지를 선택할 수 있습니다. 어느 것을 선택해도 좋습니다. 보통은 실수 부분인 코사인 함수를 선택합니다. 저는 사인형 변수의 기본형을 코사인으로 기술할 것이기 때문에 실수 부분을 선택하겠습니다. 다음과 같은 사인형 변수를 생각해봅시다.

 $$
x\left(t\right)=X_m\cos\left(\omega t+\theta_x\right)
 $$

 이는 다음 식의 실수 부분입니다.

 $$
 x\left(t\right)=\text{Re}\left[X_me^{j\left(\omega t+\theta_x\right)}\right]\ \ \ \text{(}X_m\text{ 은 실수라고 가정)}
 $$

 괄호 속 식은 다음과 같이 쓸 수 있습니다.

 $$
X_me^{j\left(\omega t+\theta_x\right)}=X_me^{j\omega t}e^{j\theta_x}
 $$

 $$e^{j\omega t}$$는 주파수를 나타내고, $$e^{j\theta_x}$$은 위상을 나타냅니다. 주파수는 전원에서 바꾸지 않는 이상 회로 내부의 동작으로는 변하지 않습니다. 따라서 우리는 진폭과 위상에 대한 정보만 알면 됩니다. **위상자(Phasor)**를 다음과 같이 정의합니다.

 $$
 \begin{align*}
\mathbf{X}&=X_me^{j\theta_x}\\
&=X_m\angle\theta_x
\end{align*}
 $$

 표기법은 둘 중 편한 것으로 사용하시면 됩니다. 이는 다음의 **위상자 변환(Phasor Transform)**을 통해 도출되는 양입니다.
 
 $$
\mathbf{X}=\mathcal{P}\left[X_m\cos\left(\omega t+\theta_x\right)\right]
 $$

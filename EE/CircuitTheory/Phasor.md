# 위상자

---

## 오일러 공식

삼각 함수끼리의 연산은 비교적 복잡합니다. 지수 함수로 바꿀 수 있다면 연산이 더 편리해집니다. 이는 오일러 공식(Euler's Formula)을 이용하면 됩니다. 오일러 공식은 지수 함수와 삼각 함수 사이의 관계식을 나타냅니다.

$$
e^{j\theta}=\cos\theta+j\sin\theta
$$

### 유도

$$e^x$$의 테일러 전개는 다음과 같습니다.

$$
e^x=\sum_{k=0}^{\infty}\frac{x^k}{k!}
$$

이 식에서 $$x=j\theta$$를 대입하면 다음과 같습니다.

$$
\begin{align*}
		e^{j\theta}&=\sum_{k=0}^{\infty}\frac{\left(j\theta\right)^k}{k!}\\
		&=\frac{1}{0!}+\frac{j\theta}{1!}+\frac{-\theta^2}{2!}+\frac{-j\theta^3}{3!}+\frac{\theta^4}{4!}+\frac{j\theta}{5!}\cdots\\
		&=\left(\frac{1}{0!}+\frac{-\theta^2}{2!}+\frac{\theta^4}{4!}+\cdots\right)+\left(\frac{j\theta}{1!}+\frac{-j\theta^3}{3!}+\frac{j\theta^5}{5!}+\cdots\right)\\
		&=\left(\frac{1}{0!}+\frac{-\theta^2}{2!}+\frac{\theta^4}{4!}+\cdots\right)+j\left(\frac{\theta}{1!}+\frac{-\theta^3}{3!}+\frac{\theta^5}{5!}+\cdots\right)\\
		&=\sum_{k=0}^{\infty}\frac{\left(-1\right)^k\theta^{2k}}{\left(2k\right)!}+j\sum_{k=0}^{\infty}\frac{\left(-1\right)^k\theta^{2k+1}}{\left(2k+1\right)!}\\
		&=\cos\theta+j\sin\theta\\
	\end{align*}
 $$

 $$
 \begin{align*}
 \rightarrow e^{j\theta}=\cos\theta+j\sin\theta
 \end{align*}
 $$

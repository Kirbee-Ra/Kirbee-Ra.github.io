# 쌍선형 형식

---

## 쌍선형 형식

쌍선형 형식(Bilinear Form)이란 체 $$\mathbb{F}$$위의 벡터 공간 $$V$$에 대해 다음의 사상

$$
\begin{align*}
B:V\times V\rightarrow\mathbb{F}
\end{align*}
$$

이 $$V$$의 임의의 벡터 $$u,v,w$$와 $$\mathbb{F}$$의 임의의 원소 $$\alpha,\beta$$에 대해

$$
\begin{align*}
B\left(\alpha u+\beta v,w\right)=\alpha B\left(u,w\right)+\beta B\left(v,w\right)\\
\text{and}\\
B\left(u,\alpha v+\beta w\right)=\alpha B\left(u,v\right)+\beta B\left(u,w\right)
\end{align*}
$$

을 만족하는 사상입니다. 쉽게 말하면, 각 벡터에 대해 각각 선형성을 지닌 사상입니다. 다음과 같이 실수를 체로 갖는 벡터 공간의 두 벡터의 내적은 쌍선형 형식이 될 수 있습니다.

$$
\begin{align*}
\langle \alpha u+\beta v,w \rangle=\alpha\langle u,v\rangle+\beta\langle v,w\rangle
\end{align*}
$$

복소수를 체로 갖는다면 쌍선형 형식이 될 수 없습니다.

---

## 쌍선형 형식의 행렬 표현

$$n$$차원 벡터 공간 $$V$$이 $$\left\{\hat{e}_i\right\}$$를 기저로 갖는다고 해봅시다. 모든 쌍선형 형식 $$B$$는 다음과 같이 $$n\times n$$ 행렬 $$\mathbf{M}$$으로 나타낼 수 있습니다.

$$
B\left(x,y\right)=\mathbf{x}^T\mathbf{M}\mathbf{x}=\begin{bmatrix}
		x_1&\cdots&x_n
	\end{bmatrix}\begin{bmatrix}
	M_{11}&\cdots&M_{1n}\\
	\vdots&&\vdots\\
	M_{n1}&\cdots&M_{nn}
	\end{bmatrix}
	\begin{bmatrix}
		y_1\\
		\vdots\\
		y_n
	\end{bmatrix}
$$

여기서 $$\mathbf{x},\mathbf{y}$$는 $$V$$의 원소 $$x,y$$의 열벡터 표현입니다.

---

## 대칭성 및 반대칭성

쌍선형 형식 $$B$$가 다음을 만족하면 대칭적(Symmetric)이라고 말합니다.

$$
B\left(u,v\right)=B\left(v,u\right)
$$

행렬로 표현하면 다음과 같습니다.

$$
\mathbf{M}=\mathbf{M}^T
$$

다음을 만족하면 반대칭적(Skew-Symmetric)이라고 말합니다.

$$
B\left(u,v\right)=-B\left(v,u\right)
$$

행렬로 표현하면 다음과 같습니다.

$$
\mathbf{M}=-\mathbf{M}^T
$$

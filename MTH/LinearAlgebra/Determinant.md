# 행렬식

---

## 행렬식

체 $$\mathbb{F}$$ 위의 $$n$$차원 벡터 공간 $$V$$에 대해 다음의 선형 변환 $$A$$를 생각해봅시다.

$$
A:V\rightarrow V
$$

행렬 형태로는, $$A$$는 $$n\times n$$ 행렬입니다. 행렬식(Determinant)이란 다음의 특성을 따르는 $$A$$에 관련된 스칼라입니다.

$$
\begin{align*}
	&\text{1. }\text{det}\left(\mathbf{I}\right)=1\\
	&\text{2. }\text{det}\left(\mathbf{AB}\right)=\text{det}\left(\mathbf{A}\right)\text{det}\left(\mathbf{B}\right)\\
	&\text{3. Determinant is a multilinear function in the rows (or columns) of the matrix.}\\
	&\text{4. Swapping any two rows (or columns) of the matrix multiplies the determinant by }-1.
\end{align*}
$$

행렬식이 $$0$$이 아니라면, 그 행렬은 역행렬이 존재합니다.

---

## 평행육면체의 부피

실공간에서 행렬식은 그 행렬의 열벡터가 이루는 평행육면체의 부피와 같습니다.

# 벡터 공간

---

## 체
체(Field, $$\mathbb{F}$$)란 교환성, 결합성, 항등원, 역원, 분배성을 만족하는 곱셈과 덧셈을 가진 집합입니다. 물리학에서는 주로 실수($$\mathbb{R}$$)나 복소수($$\mathbb{C}$$)가 스칼라의 체로 쓰입니다.

---

## 벡터 공간
만약 다음의 연산

$$
\begin{gather*}
+:V\times V\rightarrow V,\ \ \ \cdot:\mathbb{F}\times V\rightarrow V
\end{gather*}
$$

이 존재하고, 다음의 벡터 공간에 대한 공리


$$
\begin{align*}
&{1. }\forall u,v,w \in V:\left(u+v\right)+w=u+\left(v+w\right)\\
&{2. }\forall u,v\in V:u+v=v+u\\
&{3. }\exists0\in V:v+0=v\ \forall v\in V\\
&{4. }\forall v\in V,\exists-v\in V:v+\left(-v\right)=0\\
&{5. }\forall\alpha,\beta\in\mathbb{F},\forall v\in V:\left(\alpha\beta\right)v=\alpha\left(\beta v\right)\\
&{6. }1\cdot v=v\\
&{7. }\forall\alpha,\beta\in \mathbb{F},\forall v\in V:\left(\alpha+\beta\right)v=\alpha v+\beta v\\
&{8. }\forall\alpha\in\mathbb{F},\forall u,v\in V:\alpha\left(u+v\right)=\alpha u+\alpha v
\end{align*}
$$

를 만족하는 집합 $$V$$를 벡터 공간(Vector Space)이라고 합니다. 대표적으로 $$\mathbb{R}^3$$과 같은 3차원 공간이 있습니다.

---

## 부분 공간
집합 $$V$$의 부분 집합 $$W$$이 $$V$$와 같이 벡터 공간이라면, $$W$$를 부분 공간(Subspace)이라고 합니다. 부분 공간 또한 덧셈과 스칼라 곱에 대해 닫혀있습니다. 

---

## 선형 결합
스칼라 $$\alpha_i\in\mathbb{F}$$에 대한 벡터 $$v_i\in V$$의 선형 결합(Linear Combination)은 다음과 같이 표현됩니다.

$$
\begin{align*}
\left(\text{Linear Combination}\right)=\sum_{i=1}^k\alpha_iv_i=\alpha_1v_1+\alpha_2v_2+\cdots+\alpha_kv_k
\end{align*}
$$

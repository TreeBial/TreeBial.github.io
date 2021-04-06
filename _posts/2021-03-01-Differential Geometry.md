---
title: "미분기하학 정리"
categories:
  - Math
    - Differential Geometry
tags:
  - Math
  - Differential Gemometry
  - do Carmo
toc: true
use_math: true
---

# IFT
> Conditions
> - $F : U \subset \mathbf{R}^{n} \rightarrow \mathbf{R}^{n}$ is differentiable. (same dimension)
> - $dF_{p} : \mathbf{R}^{n} \rightarrow \mathbf{R}^{n}$ is an isomorphism.
> 
> Results
> - $p \in \exist V$ and $F(p) \in \exist W$ s.t. $F:V \rightarrow W$ has a differentiable inverse $F^{-1}:W \rightarrow V$.
> - $d(F^{-1})_{F(p)} = (dF_{p})^{-1}$

# 2-3. Change of Parameters; Differentiable Functions on Surfaces
Surface 위의 함수의 미분을 정의한다. Surface $S$의 점 $p$에 대하여, $p$의 미분은 당연히 $p$를 덮는 parametrization에 의존적일 수밖에 없다. 그런데 $p$의 parametrization이 유일할 리 없으니, parametrization이 다르더라도 $p$의 미분은 유일하게 결정된다는 것을 보장하기 위한 Lemma를 먼저 봐야 한다.

> **Proposition 1. Change of Parameters**  
> $p \in S$와 두 parametrization $\mathbf{x}:U \rightarrow S$, $\mathbf{y}:V \rightarrow S$가 있다. 당연히 $p$는 두 parametrization의 image에 모두 속해야 하므로 $p \in \mathbf{x}(U) \cap \mathbf{y}(V) = W$이다. 그러면 $\mathbf{y}$를 타고 $\mathbf{x}$로 넘어가는 함수 $h = \mathbf{x}^{-1} \circ \mathbf{y}$는 diffeomorphism이다.

이제 surface 위에서 정의된 함수의 미분가능성의 정의를 보자.

> **Definition. Differentiable of function on Surface**  
> 함수 $f: V \subset S \rightarrow \mathbb{R}$는 점 $p$에서 미분가능하다는 것은 $p$의 parametrization $\mathbf{x}: U \subset \mathbb{R}^2 \rightarrow S$이 존재하여 $f \circ \mathbf{x}$가 $\mathbf{x}^{-1}$에서 미분가능하다는 것이다. (단, $\mathbf{x}(U) \subset V$)

> **Example 1**

> **Definition. Differentiable between Surfaces**

> **Example 2**

> **Exmaple 3**  
> 두 surface $S_{1}$과 $S_{2}$를 생각하자. $S_{1}$를 덮는 open cover $V$와 그 위의 함수 $\varphi:V \rightarrow \mathbb{R}^3$가 differentiable이고 $\varphi(S_{1}) \subset S_{2}$를 만족하면 restriction $\varphi \big|_{S_{1}}$도 differentiable이다.

> **Definition. Regular Curve**

> **Example 4. Surface of Revolution**

# 2-4. The Tangent Map
$S$ 위의 임의의 differentiable curve $\alpha$에 대해 $\alpha'(0)$을 **tangent vector**라 한다.

> **Proposition 1**  
> $d\mathbf{x}_{q}(\mathbb{R}^{2}) = (\text{the set of tangent vectors})$

그런데 식의 우변은 parametrization에 독립적이므로, 다음과 같은 corollary를 얻는다. 

> **Corollary**  
> $d\mathbf{x}_{q}(\mathbb{R}^{2})$는 parametrization에 독립적이다. 즉, 두 parametrization $\mathbf{x}$와 $\mathbf{y}$가 있다면 $d\mathbf{x}_{q}(\mathbb{R}^{2}) = d\mathbf{y}_{q}(\mathbb{R}^{2})$이다.

한편 proposition 1에 나온 set of tangent vectors를 다음과 같이 새롭게 정의할 수 있다.

> **Definition. Tangent Plane**  
> $T_{p}S = d\mathbf{x}_{q}(\mathbb{R}^{2})$

# 2-5. The Fundamental Form

$\left\langle A, B \right\rangle _ {p}$

Note. Helicoid Surface
$\mathbf{X}: (u, v) \rightarrow (v \cos u, v \sin u, au)$
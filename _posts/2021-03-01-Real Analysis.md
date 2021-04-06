---
Title: "실변수함수론 정리"
categories:
  - Math
    - Real Analasys
Tag:
  - Math
toc: true
use_math: true
---

# 4주 construction of lebesgue measure
## Caratheodory Extension Theorem
### Definition 5.3.
> Def 5.3. Outer Measure  
> algebra $\mathcal{A}$와 그 위의 premeasure $\mu$에 대해서 outer measure $\mu^{\ast}: \mathcal{P}(X) \rightarrow \left[0, \infty \right]$을 다음과 같이 정의한다.
> $$\mu^{\ast}(E) = \inf \left\{ \sum_{i} \mu(A_{i}) : A_{i} \in \mathcal{A} \text{ and } E \subseteq \bigcup_{i} A_{i} \right\}$$

### Note
$\mu^{\ast}$의 정의를 이용해 계산에 필요한 몇 가지 도구를 알아보자.
1. $E$의 cover $A_{i}$를 충분히 작게 잡을 수 있다. 즉, $\forall \epsilon > 0$, $\exists A_{i} \in \mathcal{A}$ s.t. $A_{i}$ covers $E$ and $\mu^{\ast}(E) < \sum_{i} \mu(A_{i}) + \epsilon$이다.

### Proposition 5.4.
1. $\mu^{\ast}(\phi) = 0$
1. $\mu^{\ast}(A) \le \mu^{\ast}(B)$ for $A \subseteq B$
1. $\mu^{\ast}(\cup_{i} A_{i}) \le \sum_{i} \mu^{\ast}(A_{i})$

### Remark 5.10.
$\mu^{\ast}(A) \le \mu^{\ast}(A\cap E) + \mu^{\ast}(A \cap E^{C})$임을 이미 알고 있으므로, 만약 어떤 집합 $E$가 $\mu^{\ast}$-measurable인지 체크하고 싶으면 $\mu^{\ast}(A) \ge \mu^{\ast}(A\cap E) + \mu^{\ast}(A \cap E^{C})$만 체크하면 된다.

### Theorem 5.11.
> Thm 5.11. Caratheodory Extension Theorem
> - $\mathcal{M}^{\ast}$이 $\sigma$-algebra이다.
> - $\mu^{\ast} \big|_{\mathcal{M}^{\ast}}$이 measure이다.
> - $\mu^{\ast}\big|_{\mathcal{A}} = \mu$
> - $\mathcal{A} \subset \mathcal{M}^{\ast}$  
> 특히, $\mathcal{A}$를 포함하는 가장 작은 $\sigma$-algebra를 $\mathcal{M}$이라 하면 $\mathcal{M}$의 measure $\bar{\mu}$가 존재한다. 또한 $\mu$가 $\sigma$-finite이면 $\bar{\mu}$는 unique하다.

[증명](#-[PROOF]-Caratheodory-Extension-Theorem)


## Proofs
### [PROOF] Caratheodory Extension Theorem
[내용](#-Caratheodory-Extension-Theorem)  
증명 단계가 조금 복잡하다. $\mu^{\ast}$와 $\mathcal{M}$의 finite에 대해 먼저 증명하고, infinity로 넘어간다.

**Step 0.** $\mathcal{M}^{\ast}$이 $\sigma$-algbra(1번, 2번)이다.  
1번. $\phi \in \mathcal{M}^{\ast}$  
$\mu^{\ast}(A \cap \phi) + \mu^{\ast}(A\cap\phi^{C}) = \mu^{\ast}(\phi) + \mu^{\ast}(A) = 0 + \mu^{\ast}(A)=\mu^{\ast}(A)$  
2번. $E \in \mathcal{M}^{\ast} \Rightarrow E^{C} \in \mathcal{M}^{\ast}$  
$\mu^{\ast}(A) = \mu^{\ast}(A \cap E) + \mu^{\ast}(A\cap E^{C}) = \mu^{\ast}(A \cap (E^{C})^{C}) + \mu^{\ast}(A \cap E^{C})$

**Step 1.** $\mathcal{M}^{\ast}$ is closed under finite union  
$E, F \in \mathcal{M}^{\ast}$ 두 개의 union에 대해서 닫혀있음만 보여도 충분하다. [Remark 5.10.](#-Remark-5.10.)에 의하여 $\mu^{\ast}(A) \ge \mu^{\ast}(A\cap(E \cup F)) + \mu^{\ast}(A \cap (E \cup F)^{C})$임을 증명하자.
$$\begin{aligned}\mu^{\ast}(A) &= [\mu^{\ast}(A \cap (E \cap F)) + \mu^{\ast}(A \cap (E \cap F^{C})) + \mu^{\ast}(A \cap (E^{C} \cap F))] + \mu^{\ast}(A \cap (E^{C} \cap F^{C}))\\&\ge \mu^{\ast}(A \cap (E \cup F)) + \mu^{\ast}(A \cap (E \cup F)^{C}) \end{aligned}$$
첫 번째 줄은 $E$와 $F$가 $\mathcal{M}^{\ast}$의 원소이므로 등호가 성립하고, 두 번째 줄은 [Prop 5.4.](#-Proposition-5.4.)의 3번 성질에 의해 성립한다.

**Step 2.** $\mu^{\ast}$ is finitely additive on $\mathcal{M}^{\ast}$  
($\mu^{\ast}(\phi) = 0$은 [Prop 5.4.](#-Proposition-5.4.)에서 이미 증명되었다.)  
이 역시 두 집합 $E, F \in \mathcal{M}^{\ast}$에 대해서만 증명해도 충분하다. Step 1에 의해 $E \cup F \in \mathcal{M}^{\ast}$이므로 $\mu^{\ast}(E \cup F) = \mu^{\ast}((E \cup F) \cap E) + \mu^{\ast}((E \cup F) \cap E^{C}) = \mu^{\ast}(E) + \mu^{\ast}(F)$이다.

**Step 3.** $\mathcal{M}^{\ast}$ is closed under countable union and $\mu^{\ast}$ is a measure on $\mathcal{M}^{\ast}$  
$(E_{i}) \in \mathcal{M}^{\ast}$에 대해, $\bigcup_{i} E_{i} \in \mathcal{M}^{\ast}$임을 증명해야 한다. 그런데 $F_{i} = E_{i}-(\bigcup_{n=1}^{i-1}E_{n})$을 생각하면 $F_{i}$가 disjoint이면서 필요한 모든 좋은 성질을 만족하기 때문에, disjoint family에 대한 closed 증명만으로도 충분하다. 그러므로 $(E_{i})$가 disjoint라는 조건을 추가할 수 있다.   
$F=\bigcup_{i=1}^{\infty} E_{i}$, $F_{n} = \bigcup_{i=1}^{n} E_{i}$라 하고 $F$가 $\mu^{\ast}$-m'ble임을 보이자. 임의의 $A \subseteq X$에 대해
$$\begin{aligned}\mu^{\ast}(A) &= \mu^{\ast}(A \cap F_{n}) + \mu^{\ast}(A \cap (F_{n})^{C}) && \because F_{n} \text{is } \mu^{\ast} \text{-m'ble} \\ &= \sum^{n}_{k=1} \mu^{\ast}(A \cap E_{k}) + \mu^{\ast}(A \cap (F_{n})^{C}) && \because (E_{i}) \text{ is disjoint, finite additivity of } \mu^{\ast} \\ &\ge \sum^{n}_{k=1} \mu^{\ast}(A \cap E_{k}) + \mu^{\ast}(A \cap F^{C}) && \because F_{n} \subset F \\\end{aligned}$$
이고, 양변에 $\lim_{n \to \infty}$를 취해주면
$$\begin{aligned}\mu^{\ast}(A) &\ge \sum^{\infty}_{k=1} \mu^{\ast}(A \cap E_{k}) + \mu^{\ast}(A \cap F^{C}) \\ &\ge \mu^{\ast}(A \cap F) + \mu^{\ast}(A \cap F^{C}) && \because \text{countable subadditivity of } \mu^{\ast} \end{aligned}$$
이므로 $\mu^{\ast}(A) \ge \mu^{\ast}(A \cap F) + \mu^{\ast}(A \cap F^{C})$이다. 즉, 임의의 disjoint family $(E_{i}) \in \mathcal{M}^{\ast}$에 대하여 $F = \bigcup_{i} E_{i} \in \mathcal{M}^{\ast}$이므로 $\mathcal{M}^{\ast}$은 closed under countable union이다.

한편, 위의 부등호는 모두 등호로 변환이 가능하고, $A = F = \bigcup_{i} E_{i}$를 대입해주면 마지막 두 번째 식에서
$$\mu^{\ast}(\bigcup_{i} E_{i}) = \sum^{\infty}_{i=1} \mu^{\ast}(E_{i})$$
를 얻는다. 그러므로 $\mu^{\ast}$는 measure이다.

**Step 4.** $\mu^{\ast}\big|_{\mathcal{A}} = \mu$  
1. $\mu^{\ast}(E) \le \mu(E)$  
$E \subseteq E$이므로 자명하다.

1. $\mu^{\ast}(E) \ge \mu(E)$  
임의의 $E$의 cover $(A_{n}) \in \mathcal{A}$에 대하여 $B_{n} = E \cap (A_{n} - (\bigcup^{n-1}_{i=1} A_{i}))$이라 하면 각 $B_{n}$은 disjoint이고 그 union은 $E$이다. 그러므로
$$\begin{aligned} \mu(E) &= \sum^{\infty}_{n=1} \mu(B_{n}) && \because \text{countable additivity of premeasure} \\ &\le \sum^{\infty}_{n=1} \mu(A_{n}) \end{aligned}$$
이고, $\mu^{\ast}$은 $\sum \mu(A_{n})$의 infimum으로 정의되므로 $\mu^{\ast}(E) \ge \mu(E)$이다.

**Step 5.** $\mathcal{A} \subset \mathcal{M}^{\ast}$  
임의의 $E \in \mathcal{A}$와 $A \in X$에 대하여 $\mu^{\ast}(A) \ge \mu^{\ast}(A \cap E) + \mu^{\ast}(A \cap E^{C})$임을 증명하자. [Note](#-Note)에 의해 $A_{i} \in \mathcal{A}$를 $\sum \mu(A_{i}) \le \mu^{\ast}(A) + \epsilon$이 되게 잡을 수 있다. 그러므로
$$\begin{aligned}\mu^{\ast}(A) + \epsilon &\ge \sum_{i} \mu(A_{i}) \\ &= \sum_{i} \left[ \mu(A_{i} \cap E) + \mu(A_{i} \cap E^{C})\right] && \because \mu \text{ is measure} \\ &\ge \mu^{\ast}(A \cap E) + \mu^{\ast}(A \cap E^{C}) && \because A_{i} \text{ covers } A \text{, and by definition of } \mu^{\ast}\end{aligned}$$
이다. 그런데 임의의 양수 $\epsilon$에 대해 성립하는 것이므로 $\mu^{\ast}(A) \ge \mu^{\ast}(A \cap E) + \mu^{\ast}(A \cap E^{C})$이라 할 수 있다.

**Step 6.** uniqueness of extension
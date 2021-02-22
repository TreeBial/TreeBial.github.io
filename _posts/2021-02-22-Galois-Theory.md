---
Title: "[현대대수학] Galois Theory"
Categories:
  - Math
    - Abstract Algebra
Tag:
  - Math
  - 수학
  - Abstract Algebra
  - 현대대수학
  - Galois Theory
  - Fraleigh
---

# Motivation

Fraleigh 책에서는 **Normal Extension**과 **Galois Theory**를 위해 48장부터 52장까지 몇 가지 개념들을 쌓아 올린다. automorphism extension theorem, splitting field, separable field 등이 그것이다. (splitting field는 $\left\vert G(E/F) \right\vert = \left\{ E:F \right\}$로, separable field는 $\left\{ E:F \right\} = [E:F]$로 대표될 수 있음을 기억하자.)

하지만 이 개념들은, 그 자체만으로 매우 강력한 성질을 가지고 있다고 보기 힘들다. 하지만 이 둘을 합친, 즉 splitting인 동시에 separable인 field는 **Normal Extension**이라는 이름이 따로 붙을 정도로 매우 강력한 성질을 가지고 있으며, 그 강력한 성질을 규명한 것이 바로 **Galois Theory**이다.

# Contents

## Normal Extension의 정의와 기본 성질

> **Definition.** Finite Normal Extension  
> $F$의 finite extension $E$가 $F$의 splitting field인 동시에 separable field이면 **Finite Normal Extension**이라 한다.

'finite'을 한정한 것에 주목하자. 책에서는 $E$가 infinite extension인 경우를 다루지 않는다. 그리고 위 정의로부터 몇 가지 기본적인 성질들을 증명할 수 있다.

> **Theorem.**
> $K$가 $F$의 finite normal extension이고 $E$가 $F \le E \le K$인 field이면 다음과 같은 성질들을 만족한다.
> - $K$는 $E$의 normal extension이다.
> - $G(K/E)$는 $G(K/F)$의 subgroup이다.
> - $G(K/F)$를 $G(K/E)$로 left coset을 쪼갤 수 있는데, automorphism $\sigma$와 $\tau$가 같은 coset의 원소이면 임의의 $a \in E$에 대하여 $\sigma(a) = \tau(a)$이다.

> **Note.** $E$는 $F$의 normal extension이 아닐 수 있다. Splitting field에서와 같은 예시, 즉 $F = \mathbb{Q}$, $E=\mathbb{Q}(\sqrt[3]{2})$, $K=\mathbb{Q}(\sqrt[3]{2}, \sqrt{3}i)$를 생각하자.

개인적으로는, 여기까지만으로도 의미가 있는 정리라고 생각한다. field 사이의 관계와 $G(K/F)$ 등의 group 사이의 관계를 보여주는, 그 중에서도 가장 기본적인 subgroup 관계를 다루는 정리이기 때문이다. left coset 성질은 여기에서 파생되는 부수적인 성질이라 생각한다.

하지만 여기에 더욱 강력한 성질을 증명할 수 있는데, 이것이 **Galois Theory**이다.

## Galois Theory

Galois Theory를 한 문장으로 요약하면 다음과 같다. (Fraleigh 책의 내용을 임의대로 요약한 것이다.)
> field $F$와 $F$의 finite normal extension $K$를 생각하자. 그러면 $F$와 $K$ 사이의 임의의 field와 $G(K/F)$와 $G(K/K)=\left\{ e \right\}$ 사이의 임의의 group에 대해서 일대일대응 관계가 성립한다.

$G(K/K)$가 trivial group이기 때문에 $G(K/F)$와 $G(K/K)$ '사이의' group이라는 표현이 어색할 수도 있다. 그냥 $G(K/F)$의 subgroup이라 하면 될 것을 굳이? 하지만 이는 field에서 '사이'라는 표현이 사용되는 것에 대응되도록 쓴 표현이다.

수학을 공부할 때 가장 짜릿한 순간은, 어렵게 어렵게 쌓아올린 수학의 한 분야가 다른 분야와 어떤 연관관계가 있는지 밝혀질 때이다. Galois Theory는 결국 abstract algebra라는 분야 안에서의 '대응관계'이기 때문에 별로 커 보이지 않을 수도 있지만, field를 다루는 것과 group을 다루는 것 사이에 아주 강력한 연관관계를 제공해주기에 매우 중요하다고 생각한다. 

이제 책에 언급된 Galois Theory를 정리해보자.

> **Theorem.** Galois Theory  
> field $F$와 그 finite normal extension $K$를 하자. $F$와 $K$ 사이의 field와 $G(K/F)$의 부분집합 사이에 다음과 같은 관계를 생각하자.
> - field $E$ -> $G(K/E)$ = $\lambda(E)$
> - subgroup $H$ -> $K_{H}$
> 
> 그러면 두 관계는 서로 일대일대응이며 역함수 관계가 성립한다. 즉, $E = K_{G(K/E)} = K_{\lambda(E)}$ 이고 $H = G(K/K_{H})$이다.  
> 또한 다음과 같은 성질들이 성립한다.
> - $E$도 $F$의 normal extension이면, $G(K/E)$는 $G(K/F)$의 normal subgroup이고, $G(E/F) \cong G(K/F) / G(K/E)$이다.
> - field diagram과 group diagram을 그리면 역순으로 완전히 일치한다.

$K$와 $F$에 대해 subfield diagram을 그리고, $G(K/F)$와 $G(K/K)$에 대해 subgroup diagram을 그리면 서로 완전히 역순을 이룬다는 것은 field를 다루는 데에 있어 아주 강력한 직관을 제공한다. 예를 들어 만약 $G(K/F) \cong \mathbb{Z}_{12}$인 $K$와 $F$가 있다면, 우린 이미 $\mathbb{Z}_{12}$의 구조를 알고 있기에 $K$와 $F$의 모든 field들도 구조화할 수 있다는 것을 의미한다.

## Finite Field의 Galois Theory

여긴 나중에 정리
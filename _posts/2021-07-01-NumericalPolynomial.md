---
title: Numerical Polynomials
description: "Numerical polynomial의 정의 및 성질에 관한 글"
lead: "Numerical polynomial의 정의 및 성질에 관한 글"
date: 2021-06-08
lastmod: 2021-06-08
draft: false
weight: 50
contributors: ["Jeongwoo Park"]
---

## Definition and Examples

Numerical polynomial은 다음처럼 정의됩니다.

>**Definition 1** ([numerical polynomial](https://en.wikipedia.org/wiki/Integer-valued_polynomial)). Polynomial $f \in \mathbb{Q}[X]$가 $f (\mathbb{Z}) \subseteq \mathbb{Z}$를 만족하면, 이를 *numerical polynomial* 혹은 *integer-valued polynomial*이라고 부릅니다.

>**Examples 2**.
>1. 정수계수 다항식은 numerical polynomial입니다.
>2. 정수 $d$에 대해, $\binom{X}{d} = \frac{X(X-1) \cdots (X-d)}{d!}$는 numerical polynomial입니다.

대수적 측면에서, numerical polynomial들의 algebraic combination은 다시 numerical polynomial이 됩니다.

>**Proposition-Definition\* 3**. 집합
>$$ \operatorname{NP} (\mathbb{Z}) := \lbrace f \in \mathbb{Q}[X] \text{ is a numerical polynomial.} \rbrace $$
>은 $\mathbb{Q}[X]$의 $\mathbb{Z}$-subalgebra를 이루며, 이를 *$\mathbb{Z}$-algebra of all numerical polynomials*라고 부릅니다.

더 나아가, 이는 free $\mathbb{Z}$-module을 이루며, $\lbrace \binom{X}{d} \rbrace_{d \in \mathbb{N}}$이 basis를 이룹니다.

>**Exercise 4**. $\lbrace \binom{X}{d} \rbrace_{d \in \mathbb{N}}$가 $\operatorname{NP}(\mathbb{Z})$의 $\mathbb{Z}$-basis를 이룬다는 것을 증명해주세요. (힌트. $\Delta: f(n) \mapsto f(n+1)-f(n)$와 수학적 귀납법.)

## Topological Property

<a name = "name"></a> 여기서, 이런 질문을 생각해볼 수 있습니다: *$f \in \mathbb{Q}[X]$가 유한히 많은 경우를 제외하고는 정수를 내놓는다면 numerical polynomial일까?*

이는 기초적인 정수론 지식으로 증명할 수 있습니다. 여기서는 이를 좀 더 발전시킨 증명을 소개하겠습니다.

다음 명제가 성립합니다.

>**Definition\* 5** (Furstenberg topology). 정수 $a,b$에 대해,
>$$ S(a,b) := \lbrace an+b \rbrace_{n \in \mathbb{Z}} $$
>를 정의합니다. $\mathbb{Z}$ 위에, $\lbrace S(a,b) \rbrace_{a \neq 0}$을 open base로 하는 topology를 정의할 수 있으며, 이를 *Furstenberg topology*라고 합니다. (이 topology는 [Furstenberg의 소수 무한성 증명](https://en.wikipedia.org/wiki/Furstenberg%27s_proof_of_the_infinitude_of_primes)에 등장합니다.)

>**Proposition**. $f \in \mathbb{Q}[X]$가 numerical polynomial일 때, $f:\mathbb{Z} \to \mathbb{Z}$는 continuous입니다. 여기서, $\mathbb{Z}$ 위의 topology는 Furstenberg topology입니다.

**Proof**. $N \cdot f \in \mathbb{Z}[X]$인 $N \neq 0$에 대해, $f(S(a,Nb)) \subseteq S(f(a),b)$이므로 당연합니다. C.Q.F.D.

[앞에서 했던 질문](#name)과 다음이 동치임을 쉽게 알 수 있습니다: *$f$가 numerical polynomial, 그리고 $N$이 정수라고 하자. 만일 거의 모든 정수에 대해 $f$가 $N$의 배수를 내놓는다면, $f$는 항상 $N$의 배수를 내놓는다.* 이 명제를 다음처럼 보일 수 있습니다.

**Proof**. Frustenberg topology에서 $N \mathbb{Z}$는 closed이므로, $f^{-1}(N \mathbb{Z})$는 closed set이어야 합니다. 그런데, cofinite set의 closure는 $\mathbb{Z}$이고, 따라서 증명이 끝납니다. C.Q.F.D.

즉, 어떤 polynomial over $\mathbb{Q}$가 numerical임을 보이기 위해서는 한 [Frustenberg topology에서 dense한 set] 위에서 정수임을 체크하면 충분합니다. 이러한 집합에는 다음이 있습니다.

>**Examples**
>0. cofinite set은 dense합니다.
>1. $\mathbb{Z}_{\ge n}$은 dense합니다.
>2. complement가 arithmetic progression을 포함하지 않는 집합은 dense합니다. 이것의 역 또한 성립합니다.
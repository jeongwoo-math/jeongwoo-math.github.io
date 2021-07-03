---
title: Numerical Polynomials
date: 2021-06-08
classes: wide
categories:
- topology
tags:
- numerical polynomial
---

> Numerical polynomial --- (거의) 모든 정수에 대해, 정수값을 내놓는 다항식.

## 정의

Numerical polynomial은 다음처럼 정의됩니다.

\> <ins>**Definition 1**</ins> ([numerical polynomial](https://en.wikipedia.org/wiki/Integer-valued_polynomial)). 다항식 $f \in \mathbb{Q}[X]$가 $f (\mathbb{Z}) \subseteq \mathbb{Z}$를 만족하면, 이를 *numerical polynomial* 혹은 *integer-valued polynomial*이라고 부릅니다.

\> <ins>**Examples 2**</ins>.

1. 정수계수 다항식은 numerical polynomial입니다.
2. 정수 $d$에 대해, $\binom{X}{d} = \frac{X(X-1) \cdots (X-d+1)}{d!}$는 numerical polynomial입니다.

그런데, $f(n) \in \mathbb{Z}$ for all but finitely many $n \in \mathbb{Z}$이지만 $f$가 numerical polynomial이 아닌 예시는 찾기 쉽지 않습니다. 사실, 이러한 예시는 없습니다. 즉, <ins>다항식이 거의 모든 정수에 대해 정수값을 내놓는다면, numerical polynomial이어야만 합니다!</ins> ($\dagger$)

\> <ins>**Remark 3**</ins>. 임시적으로, 이 경우에 '거의 모든'은 '유한히 많은 경우를 제외하고'를 의미합니다. 정확한 정의는 후에 소개됩니다.

이러한 성질은 연속함수에서도 발견됩니다. 어떤 연속함수가 '거의 모든' 점에서 $0$이라면, 어디에서나 $0$이 되는 것처럼 말이지요. 이 경우, '거의 모든'은 '어떤 (고정된) dense set 위의'라는 의미로 이해될 수 있습니다. 놀라운 점은, (추상적인) 위상수학을 이용한다면 numerical polynomial의 저 성질($\dagger$) 역시 같은 방식으로 증명될 수 있다는 것입니다!

## Topological Property

다음 명제가 성립합니다.

\> <ins>**Definition\* 4**</ins> (Furstenberg topology). 정수 $a,b$에 대해,
$$ S(a,b) := \lbrace an+b \rbrace_{n \in \mathbb{Z}} $$
를 정의합니다. $\mathbb{Z}$ 위에, $\lbrace S(a,b) \rbrace_{a \neq 0}$을 open base로 하는 topology를 정의할 수 있으며, 이를 *Furstenberg topology*라고 합니다.

\> <ins>**Remark 5**</ins>. 이 topology는 [Furstenberg의 소수 무한성 증명](https://en.wikipedia.org/wiki/Furstenberg%27s_proof_of_the_infinitude_of_primes)에 등장합니다. 링크에는 이 글에서 사용할 Furstenberg topology의 기초적인 성질 역시 소개되어 있습니다.

\> <ins>**Main Proposition 6**</ins>. $f \in \mathbb{Q}[X]$가 numerical polynomial일 때, polynomial function $f:\mathbb{Z} \to \mathbb{Z}$는 continuous입니다. 여기서, $\mathbb{Z}$ 위의 topology는 Furstenberg topology입니다.

**Proof**. $N \cdot f \in \mathbb{Z}[X]$인 $N \in \mathbb{Z} \setminus 0$에 대해, $f(S(N \cdot a,b)) \subseteq S(a, f(b))$이므로 그렇습니다. //

유리계수 다항식에 영이 아닌 정수를 곱해 정수계수 다항식으로 만들 수 있습니다. 이를 이용해, numerical polynomial의 성질($\dagger$)과 다음이 동치임을 알 수 있습니다: *$f$가 numerical polynomial, 그리고 $N$이 정수라고 하자. 만일 '거의 모든' 정수에 대해 $f$가 $N$의 배수를 내놓는다면, $f$는 항상 $N$의 배수를 내놓는다.* 이 명제를 다음처럼 보일 수 있습니다.

**Proof of ($\dagger$)**. Frustenberg topology에서 $N \mathbb{Z}$는 closed이므로, inverse image $f^{-1}(N \mathbb{Z})$는 cofinite set을 포함하는 closed set이어야 합니다. 그런데, cofinite set은 Frustenberg topology에서 dense하고, $f^{-1}(N \mathbb{Z}) = \mathbb{Z}$가 성립합니다. 따라서 $f$는 항상 $N$의 배수를 내놓습니다. //

즉, 어떤 polynomial over $\mathbb{Q}$가 numerical임을 보이기 위해서는 어떤 'Frustenberg topology에 대해 dense한 set' 위에서 정수임을 확인하면 충분합니다. 즉, 앞서 말한 '거의 모든'은 사실 '어떤 dense한 set 위에서'로 해석될 수 있습니다. 이러한 집합에는 다음이 있습니다.

\> <ins>**Examples 7**</ins>.
0. cofinite set은 dense합니다.
1. $\mathbb{Z}_{\ge n} := \lbrace m \in \mathbb{Z} \,;\, m \ge n \rbrace$은 dense합니다.
2. complement가 arithmetic progression을 포함하지 않는 집합은 dense합니다. 이것의 역 또한 성립합니다.

## 여담

1. 모든 numerical polynomial은 $\mathbb{Z}$-linear combination of the binomial polynomials $\binom{X}{d}$로 유일하게 나타내어집니다. 이는

$$ \Delta: \mathbb{Z}^\mathbb{Z} \to \mathbb{Z}^\mathbb{Z} \,;\, f \mapsto \Delta(f) := [n \mapsto f(n+1) - f(n)] $$

라는 함수와, numerical polynomial의 degree에 대한 induction으로 증명됩니다.

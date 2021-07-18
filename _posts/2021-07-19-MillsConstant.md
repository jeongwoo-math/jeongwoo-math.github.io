---
title: 밀스 상수 -- 리만가설이 참일 때 근사 가능한 수.
date: 2021-07-19
classes: wide
categories:
- number theory
tags:
- mathematical constant
---

수학의 유명한 상수에는 $\pi, e, \zeta(3)$ 등이 있고, 이들 대부분은 유리수 근삿값이 알려져 있습니다. 하지만, 이러한 근삿값이 알려지지 않은 수학 상수도 있습니다. [Mills' constant](https://en.wikipedia.org/wiki/Mills%27_constant)처럼 말이죠. 재미있게도, 이 상수는 [리만 가설](https://en.wikipedia.org/wiki/Riemann_hypothesis)을 가정한다면 근사가 가능해집니다. 이 글에서는 이 상수의 정의와 variation에 대해 알아볼 것입니다.

## Legendre Conjecture

정수론에는 다음의 유명한 정리가 있습니다.

\> <ins>**Theorem 1**</ins> ([Bertrand's postulate](https://en.wikipedia.org/wiki/Bertrand%27s_postulate)) $2$ 이상의 자연수 $n$에 대해, $n$과 $2n$ 사이에는 소수가 존재합니다.

이 정리는 다양한 방법으로 증명되었으며, [여기](https://en.wikipedia.org/wiki/Proof_of_Bertrand%27s_postulate)에도 소개되어 있습니다. 하지만, 이것과 유사한 다음 명제는 아직 해결되지 않았습니다.

\> <ins>**Conjecture 2**</ins> ([Legendre conjecture](https://en.wikipedia.org/wiki/Legendre%27s_conjecture)) $1$ 이상의 자연수 $n$에 대해, $n^2$과 $(n+1)^2$ 사이에는 소수가 존재합니다.

그러나, 이보다 조금 더 쉬워보이는 다음 명제는 증명되어 있습니다.

\> <ins>**Theorem 3**</ins> 충분히 큰 자연수 $n$에 대해, $n^3$과 $(n+1)^3$ 사이에는 소수가 존재합니다.

**Proof**. 다음 정리가 알려져 있습니다.

\> <ins>**Lemma 4**</ins> (Ingham, \[Ing1937\]) 상수 $K>0$가 있어서, 부등식 $p_{n+1} - p_n < K \cdot p_n^{5/8}$이 성립합니다. 여기서, $p_n$은 $n$번째 소수를 나타냅니다.

$n$이 $K^8$보다 큰 자연수라고 하고, $p_m$을 $n^3$ 이하의 가장 큰 소수라고 합시다. 그러면,

$$ n^3 < p_{m+1} < p_m + K \cdot p_m^{5/8} < n^3 + K \cdot n^{15/8} < n^3 + n^2 < (n+1)^3 $$

이 되어 증명이 끝납니다. //

## Mills' Constant

밀스 상수는 다음으로 정의됩니다.

\> <ins>**Definition 5**</ins> (Mills' constant) $\lfloor A^{3^n} \rfloor$가 모든 양의 정수 $n$에 대해 소수가 되는, 가장 작은 양수 $A$를 *밀스 상수*라고 합니다.

이 상수의 존재성을 증명해봅시다. \[Mil1947\]를 따라갑니다.

**Proof**. 밀스 상수의 존재성을 증명하기 위해서는, $\lfloor A^{3^n} \rfloor$가 항상 소수가 되게 하는 양수 $A$가 존재함을 보이면 충분합니다. (왜 그럴까요?)

**Lemma 4**에 의해, 소수들의 수열 $P_1, P_2, \cdots$이 있어서 다음을 만족합니다:

$$ P_n^3 < P_{n+1} < (P_n+1)^3 $$

수열 $u_n$과 $v_n$을

$$ u_n = P_n^{3^{-n}} $$

과

$$ \qquad v_n = (P_n+1)^{3^{-n}} $$

으로 정의하면, $u$는 강한 증가수열, $v$는 강한 감소수열이 되며, $u_n < v_n$이 성립합니다. 즉, $u_n$은 위로 유계인 증가수열이며, 따라서 수렴합니다. 이 수렴값을 $A$라고 한다면, $u_n < A < v_n$이 되며, 이는 $P_n < A^{3^n} < P_n+1$를 의미합니다. 따라서, $\lfloor A^{3^n} \rfloor = P_n$은 항상 소수가 되어, 증명이 끝납니다. //

## 여담

- 밀스 상수의 유리수 근삿값은 알려지지 않았지만, 리만가설을 가정한다면 이 값은 $1.3063778838630806904686144926\dots$입니다. 이 수가 유리수인지 여부는 알려지지 않았으며, 만일 유리수인 경우, 큰 소수를 쉽게 찾을 수 있게 됩니다.
- 밀스 상수 $A$에 대해, $\lfloor A^{3^n} \rfloor$ 꼴의 소수를 *밀스 소수*라고 하며, 리만 가설이 참일 경우의 리스트를 [여기](https://oeis.org/A051254)에서 찾아볼 수 있습니다.
- 만일, Legendre conjecture가 참이라면, 밀스 상수 정의에 등장하는 지수 $3$을 $2$로 바꾸어 유사한 상수를 정의할 수 있습니다. Matomäki는 Legendre conjecture를 가정하지 않고 이 결과를 증명하였습니다. \[Mat2010\]
- Floor function을 ceil function으로 바꾸어도 비슷한 명제가 성립합니다. \[Tót2017\]

## References

\[Ing1937\] A. E. INGHAM, ON THE DIFFERENCE BETWEEN CONSECUTIVE PRIMES, The Quarterly Journal of Mathematics, Volume os-8, Issue 1, 1937, Pages 255–266, [https://doi.org/10.1093/qmath/os-8.1.255](https://doi.org/10.1093/qmath/os-8.1.255)

\[Mil1947\] Mills, W. H. (1947). "[A prime-representing function](https://www.ams.org/journals/bull/1947-53-06/S0002-9904-1947-08849-2/S0002-9904-1947-08849-2.pdf)" (PDF). Bulletin of the American Mathematical Society. 53 (6): 604. doi:[10.1090/S0002-9904-1947-08849-2](https://doi.org/10.1090%2FS0002-9904-1947-08849-2)

\[Mat2010\] Matomäki, K. (2010). "[Prime-representing functions](https://users.utu.fi/ksmato/papers/Primerepfunc.pdf)" (PDF). Acta Mathematica Hungarica. 128 (4): 307–314. doi:[10.1007/s10474-010-9191-x](https://doi.org/10.1007%2Fs10474-010-9191-x). S2CID [18960874](https://api.semanticscholar.org/CorpusID:18960874).

\[Tót2017\] Tóth, László (2017). "[A Variation on Mills-Like Prime-Representing Functions](https://cs.uwaterloo.ca/journals/JIS/VOL20/Toth2/toth32.pdf)" (PDF). Journal of Integer Sequences. 20. p. 17.9.8. arXiv:[1801.08014](https://arxiv.org/abs/1801.08014)

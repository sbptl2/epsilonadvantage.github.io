---
layout: post
---

## Friday, September 16th

**Read Section 4 of [1]**

Reducing to $$O(k)$$ coordinates is actually quite involved. The high level of getting cordinate oracles makes sense. I hadn't thought about the fact that we can't get labels without picking up a $$\log(n)$$ dependence. Still don't quite know how to do it because it builds on a result from [2].

**Think about super constant lower bounds for junta testing (with the hope of generalizing to adaptive testers)**

Spend some time thinking about this, but I think the fact that we get to see an entire cylinder potentially makes it feel a lot harder.


**Read [3]**

Seemed like a nice, simple idea. Most of the magic seems to happen in the free probability bounds from Van Handel et al.


#### _For the future_
- Read [2]
- Does a non-adaptive tester in the $O(k)$ setting, imply one for the more general one? Can we use block style arguments? The argument in [1] is very adaptive.

#### _Overall Outlook_
Not a very productive day...

## References
[1] Iyer, V., Tal, A., & Whitmeyer, M. (2021). Junta distance approximation with sub-exponential queries. arXiv preprint arXiv:2106.00287.

[2] De, A., Mossel, E., & Neeman, J. (2019, November). Junta correlation is testable. In 2019 IEEE 60th Annual Symposium on Foundations of Computer Science (FOCS) (pp. 1549-1563). IEEE.

[3] Bansal, N., Jiang, H., & Meka, R. (2022). Resolving Matrix Spencer Conjecture Up to Poly-logarithmic Rank. arXiv preprint arXiv:2208.11286.

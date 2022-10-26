---
layout: post
---

## Friday, September 16th

**Read Section 6 of [1]**

I started the day by finally getting around to looking at the proof of the upper bound for SDP discrepancy of prefix Beck Fiala, in the hopes that it would help with the regular version. Unfortunately, the construction seems like it's the natural one for prefix discrepancy and I didn't get too much out of it.

**Attended Yaonan's Talk on Price of Anarchy for First Price Auctions**
At the theory seminar, Yaonan was talking about the price of anarchy for first price auctions. I had unrelatedly been reading a little bit on the basics of first price auctions and so I overall found the talk quite interesting. I learned about the price of anarchy (PoA) and price of stability (PoS), which consider the "cost" of the worst and best Nash Equilibria respectively in a game (compared to some bench mark). An interesting statement was made in the iid case that the Nash equilibria is unique [2]. I tried at some point to prove this in a simpler case and failed, so I now want to try again as well as maybe take a look at [2].

**Looked at First Two Sections of [3]**
Inspired by the talk, I also breifly looked at PoA bounds via Smoothness, which seemed like a nice, clean way to prove bounds in this setting.

**Tolerant Junta Testing**
In an attempt to get more intuition for tolerant junta testing, I worked out approximating the absolute value in the two dimensional setting. Counting was not optimal, as expected. (I think the optimal estimator has error $\frac{1]{6}$.) But I wasn't able to work out any interesting insights for how to construct a good estimator in higher dimensions. Unfortunately, the problem grows quite quickly, so working on even $3$ dimensions is tough.

#### _For the future_
- Uniqueness of nash in first price auction with U(0,1) values.
- Read [2]
- Think about super constant lower bounds for junta testing (with the hope of generalizing to adaptive testers)
- We can think of the discrepancy problem by thinking of the cycles as vectors in $$\mathbb{R}^{E}$$, is this useful?
- Read [4]



## References
[1] Bansal, N., Rohwedder, L., & Svensson, O. (2022). Flow Time Scheduling and Prefix Beck-Fiala. arXiv preprint arXiv:2202.02217.

[2] Chawla, S., & Hartline, J. D. (2013, June). Auctions with unique equilibria. In Proceedings of the fourteenth ACM conference on Electronic commerce (pp. 181-196).

[3] Roughgarden, T. (2015). Intrinsic robustness of the price of anarchy. Journal of the ACM (JACM), 62(5), 1-42.

[4] Bodwin, G., Dinitz, M., & Nazari, Y. (2022). Epic Fail: Emulators can tolerate polynomially many edge faults for free. arXiv preprint arXiv:2209.03675.

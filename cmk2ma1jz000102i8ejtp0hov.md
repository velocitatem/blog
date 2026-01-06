---
title: "Game Theoretic Exploration of Rio's Traffic Information Signaling Patterns"
seoTitle: "Exploration of Rio's Traffic Information Signaling Patterns"
seoDescription: "Analyzes Rio's traffic beeping using game theory, revealing its inefficiencies and informational challenges at saturated equilibrium"
datePublished: Tue Jan 06 2026 13:20:09 GMT+0000 (Coordinated Universal Time)
cuid: cmk2ma1jz000102i8ejtp0hov
slug: game-theoretic-exploration-of-rios-traffic-information-signaling-patterns
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1767705290398/ba609208-7199-4c3a-a04a-3646c5f1a142.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1767705351150/a049e98d-5d27-456b-a13a-1c3ba3ce6df9.png
tags: traffic, information, game-theory

---

In Rio de Janeiro, you will see motorcyclists lane split, especially when a red light has blocked the intersection and there all lanes queued with cars. As they go between cars they beep to let other know of their presence. this is an intended safety warning but to a pedestrian or drive it might come across as just noise with diminishing returns if over-used.

We demonstrate that the current state represents a sub-optimal Nash Equilibrium. The collective acoustic output informationally equivalent to silence, despite the high energetic cost and noise pollution. We look at this from a very naïve perspective just as an observational analysis.

## Game Theoretic Analysis

We model the dynamic between motorists as N player non-cooperative game. We specifically look at a sub-game of two drivers M one and two. Each player has two options of actions in a given state, **B** or **Q** which stand for beep or quiet. They earn a reward or payoff made of of a positive value (V) of safety with a negative cost of beeping which is almost negligible (C). This minimal cost mirrors what literature tells us to be true: costless signaling leads to informationally inefficient equilibria. Finally we take into account a parameter of degradation which helps us model the number of agents beeping (δ).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1767703267445/8cad76f8-277c-4fca-9128-b0c2b0f3702a.png align="center")

If M2 is Quiet, M1 should Beep because V − C &gt; 0. If M2 Beeps, M1 should still Beep, provided that the degraded safety V (1 − δ) − C &gt; 0. Since the cost of beeping C is functionally low (extremely low), the strategy B becomes strictly dominant. The system converges to the Nash Equilibrium (B, B) as defined in standard non-cooperative game theory. However, as N (the number of riders) increases, the total degradation δ approaches 1… The collective payoff becomes:

$$\lim_{N \to \infty} \sum U_i = N \cdot (V(1 - 1) - C) = -N \cdot C$$

This socially creates a local jamming equilibrium where the added benefit of safety is vanishing but the negligible cost still has secondary effects on the environment. Yet, no individual can rationally switch to silence without assuming maximum risk.

## Information Theoretic Analysis: Entropy

We make X be the variable representing the presence of a motorcycle and Y be the auditory signal received by the driver. In an ideal system, warnings are rare (P(beep) approx 0.05), meaning the information content of a signal is high. However, in the Rio system, the dominant strategy described above forces the probability of beeping to approach 1 (p → 1). The entropy H(Y) will regress to 0 in this model (more in the paper):

$$H(Y)\approx−(1 \log_2​1)=0 \text{bits}$$

A signal that is always present conveys zero bits of information. The driver learns nothing new about the state of the traffic from hearing a beep, simply because the beep is a constant (in practice this might not however be the dominant case).

We can further view the traffic environment as a communication channel, where the capacity C is limited by the signal to noise Ratio (SNR) according to the Shannon-Hartley theorem:

$$C = B \log_2 \left( 1 + \frac{S}{N_{oise}} \right)$$

The channel effectively becomes saturated. The acoustic energy is high, but the information transmission rate is zero.

The observed model from Rio presents a paradox where deviation from the strategy is not in the interest of a drive but creates a lock-in. Our entropy model also hints that the signal overuse creates a vanishing value.

safe riders and dangerous riders use the same signal with probability 1. Consequently, the signal fails to distinguish types. The "baseline" of beeping becomes informationally identical to a baseline of silence in a prolific use of the dominant strategy.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1767704974011/d653ad00-0145-4a56-8747-1a4b8f089b5c.jpeg align="center")

1. Cover, T. M., & Thomas, J. A. (2006). *Elements of Information Theory* (2nd ed.). Wiley-Interscience.
    
2. Crawford, V. P., & Sobel, J. (1982). Strategic information transmission. *Econometrica*, 50(6), 1431–1451.
    
3. Fudenberg, D., & Tirole, J. (1991). *Game Theory*. MIT Press.
    
4. Hardin, G. (1968). The tragedy of the commons. *Science*, 162(3859), 1243–1248.
    
5. Shannon, C. E. (1948). A mathematical theory of communication. *The Bell System Technical Journal*, 27(3), 379–423.
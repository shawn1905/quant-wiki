# Appendix A: Model-Free Implied Variance & VIX Index

> Euan Sinclair - *Volatility Trading* (Wiley Trading Series)

---

### APPENDIX A

Model-Free Implied Variance and Volatility

ur derivation of BSM made certain assumptions about the behavior of the underlying. It is also possible, given the options, to calculate a volatility that makes no such assumptions. This is referred to as model-free implied volatility and forms the basis for the pricing of variance swaps and the calculation of the VIX index. Variance swaps were based on an idea by Carr and Madan (1998). They used the entire cross-section of options, not just the at-the-money options, of a given expiration to build a portfolio whose exposure to variance was independent of the underlying price. The basic idea was further formalized by Britten-Jones and Neuberger (2000) and extended by Jiang and Tian (2005) to the case where the underlying paid dividends and the risk-free rate is nonzero. They show that the asset return’s variance between two times, T 1 and T 2 (in the risk-neutral world), is

### O

  E VT1 ,T2 = T

### ∞

C(T2 , K exp(rT2 )) − C(T1 , K exp(rT1 )) dK K2

### (A.1)

Or, if we consider the starting time to be the present, we can express this in terms of the forward price, Ft , and only using out-of-the-money options as 

### E V01 ,T

### 

  F  ∞ P(T, K) C(T, K) = exp(rT)  dK + dK  T K2 K2

### (A.2)

### F
Actually equations (A.1) and (A.2) give a model-free implied variance; when we take the square root we introduce an upward bias by Jensen’s inequality.

THE VIX INDEX The Volatility Index (VIX) was introduced by the Chicago Board Options Exchange (CBOE) in 1993. It was designed to be a benchmark index for equity market volatility. In 2003 the calculation methodology was changed to give a model-independent forward-looking volatility index: the S&P 500 option market’s expected value of volatility over the next 30 days. It is a discrete version of equation (A.2) where the integral has been approximated by a sum. As far as I know, the first study of the discrete situation was by Demeterfi et al. (1999), who examined in some detail the effect of using a finite number of strikes. A comparison of the two methodologies for constructing the VIX is given in Carr and Wu (2006). The derivation of the fair value for the VIX is readily available (see, for example, www.cboe.com), and the index values have been back-calculated to January 2, 1990. It is very useful for testing trading ideas. The VIX is calculated from a weighted strip of options by the following formula: 2  Ki exp(rT)V (Ki ) − T T Ki N

### σV2 I X =

### i=1

F = K0 + exp(rT)(C0 − P0 ) Ki =

### Ki+1 + Ki−1

F −1 K0

(A.3) (A.4) (A.5)

where r is the risk free rate T is the expiration time (which the CBOE calculates to the minute) F is the forward price of the index K 0 is the strike price immediately below the forward price Ki is the strike of the i-th out-of-the-money option V is the midprice of the corresponding option Equations (A.3) to (A.5) are applied to the first two option expirations, T 1 and T 2 , and we then interpolate to find a constant 30-day

Model-Free Implied Variance and Volatility

volatility: VIX = 100

### T1 σV2 I X1

NT2 − N30 NT2 − NT1

### + T2 σV2 I X2

N30 − NT1 NT2 − NT1

N365 N30 (A.6)

where NT is the number of minutes remaining for the appropriate contract N30 = 43,200 (30 × 1400) N365 = 525,600 (365 × 1400)

Char Count=
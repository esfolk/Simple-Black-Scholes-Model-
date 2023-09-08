# Simple-Black-Scholes-Model

Certainly! Here's a summary in a GitHub README format:

---

# Black-Scholes Model in Python (OOP Approach)

This repository contains an object-oriented implementation of the Black-Scholes model for European call and put option pricing. The code calculates the option price, as well as several Greeks (Delta, Gamma, Theta, Vega, Rho, Vanna, Charm, Volga).

## Overview

### Geometric Brownian Motion (GBM)

The Geometric Brownian Motion (GBM) is a stochastic process used to model stock prices in the Black-Scholes model. The GBM is given by:

dS = \mu S dt + \sigma S dW

where:
- `S` is the stock price.
- `μ` is the drift rate.
- `σ` is the volatility.
- `dW` is a Wiener process or Brownian motion.

### Black-Scholes Model

The Black-Scholes model is a mathematical model used to determine the theoretical price of European-style options. The formula for the Black-Scholes model is:

For Call Options:
C(S,t) = S N(d1) - K e^{-r(T-t)} N(d2)


For Put Options:
P(S,t) = K e^{-r(T-t)} N(-d2) - S N(-d1)


where:
- `N(.)` is the cumulative distribution function of the standard normal distribution.
- `d1` and `d2` are given by:
d1 = \frac{\ln(\frac{S}{K}) + (r + \frac{\sigma^2}{2})(T-t)}{\sigma \sqrt{T-t}}
d2 = d1 - \sigma \sqrt{T-t}


## Python Implementation (OOP Approach)

The code is written in an object-oriented manner, encapsulating all the data and methods related to the Black-Scholes model within a single class named `BlackScholes`.

### Features

- Calculates the price of European call and put options.
- Computes several Greeks: Delta, Gamma, Theta, Vega, Rho, Vanna, Charm, Volga.
- Adheres to good OOP principles like encapsulation, abstraction, and immutability.

### Usage

```python
from black_scholes import BlackScholes

# Create an instance for a call option
option = BlackScholes(S=100, K=100, T=1, r=0.05, sigma=0.2, option_type='call')

# Get the option price
print("Call Price:", option.price())

# Get the Delta
print("Delta:", option.delta())
```

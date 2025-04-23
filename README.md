# Implied-Volatility-Surface

This project calculates the **Black-Scholes option pricing formula**, derives the **Greeks**, and visualizes the **implied volatility surface** for a given stock ticker.

---

## Overview

Options traders often use implied volatility to understand market expectations of future price movement. This tool automates the process of:

- Pulling real market data for a given ticker (limited to AAPL without an API key)
- Pricing European-style call options using the **Black-Scholes formula**
- Deriving key **Greeks**: Delta, Gamma, Vega, Theta, and Rho
- Computing **implied volatility** using the **Newton-Raphson method**
- Plotting a 3D **implied volatility surface** over time to expiry and moneyness

---

## Key Features

- ✅ Analytical Black-Scholes pricing
- ✅ Calculation of all major option Greeks
- ✅ Implied volatility solver using numerical methods
- ✅ 3D volatility surface visualization
- ✅ Built-in support for dividend yield and interest rates
- ✅ Modular code structure for easy extension

---

## Requirements

- `numpy`
- `pandas`
- `matplotlib`
- `plotly` (optional for interactive 3D graphs)
- `jax` (for automatic differentiation and gradient computation)
- Market data access library (custom or from `MarketData.com`)

---

## How It Works

1. **Fetch Option Chain**  
   Pulls live market data from `MarketData.com`. Without an API key, only Apple (AAPL) is supported.

2. **Compute Black-Scholes Price & Greeks**  
   Uses closed-form solutions to compute option price and sensitivities.

3. **Estimate Implied Volatility**  
   Solves for the implied volatility that matches the market price using Newton-Raphson iterations:
   $$
   \sigma_{n+1} = \sigma_n - \frac{f(\sigma_n)}{f'(\sigma_n)}
   $$

4. **Plot the Volatility Surface**  
   Displays a 3D surface of implied volatilities as a function of moneyness and time to expiry.

---

## Output Example

- Option Chain with calculated IV
- 3D Volatility Surface:
  - X-axis: Moneyness \( \frac{S}{K} \)
  - Y-axis: Time to Expiry (Years)
  - Z-axis: Implied Volatility

---

## Educational Use

This repo is designed for educational purposes, helping users learn about:

- Derivatives pricing models
- Sensitivity analysis in options
- Numerical root-finding methods
- Data visualization in quantitative finance



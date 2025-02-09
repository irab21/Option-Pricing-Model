# Option-Pricing-Model

This project implements a detailed **Option Pricing Model** based on the **Black-Scholes formula** to price European options, calculate the Greeks, and derive implied volatility. The goal of this project is to demonstrate the application of quantitative finance concepts in Python for financial analysis and portfolio management.

---

## Features

1. **Option Pricing**:
   - Calculate the price of European call and put options using the Black-Scholes model.

2. **Greeks Calculation**:
   - Compute the key sensitivity metrics for options:
     - **Delta**
     - **Gamma**
     - **Vega**
     - **Theta**
     - **Rho**

3. **Implied Volatility**:
   - Extract the implied volatility (σ) of an option using numerical optimization.

4. **Python Implementation**:
   - Fully implemented in Python with clear, reusable, and well-documented code.

---

## Getting Started

### Prerequisites
- Python 3.7+
- Required libraries:
  - `numpy`
  - `scipy`
  - `matplotlib` (optional for visualizations)

Install the dependencies using:
```bash
pip install numpy scipy matplotlib
```

### Files Included
- **option_pricing.py**: Contains the implementation of the Black-Scholes model, Greeks, and implied volatility.
- **example_usage.py**: Demonstrates how to use the functions to price options and calculate sensitivities.

---

## Usage

### Example: Option Pricing
```python
from option_pricing import black_scholes

# Parameters
S = 100      # Current stock price
K = 110      # Strike price
T = 1        # Time to maturity (in years)
r = 0.05     # Risk-free rate
sigma = 0.2  # Volatility
option_type = "call"  # "put" for put option

# Calculate option price
price = black_scholes(S, K, T, r, sigma, option_type)
print(f"Option Price: {price:.2f}")
```

### Example: Greeks Calculation
```python
from option_pricing import calculate_greeks

greeks = calculate_greeks(S, K, T, r, sigma, "call")
print("Greeks:", greeks)
```

### Example: Implied Volatility
```python
from option_pricing import implied_volatility

market_price = 5  # Observed market price of the option
iv = implied_volatility(S, K, T, r, market_price, "call")
print(f"Implied Volatility: {iv:.2%}")
```

---

## Key Concepts

### Black-Scholes Formula
The Black-Scholes model provides a closed-form solution for pricing European call and put options. It assumes constant volatility, no dividends, and continuous trading.

- **Call Option Formula**:
  ```math
  C = S_0 \cdot N(d_1) - K \cdot e^{-rT} \cdot N(d_2)
  ```
- **Put Option Formula**:
  ```math
  P = K \cdot e^{-rT} \cdot N(-d_2) - S_0 \cdot N(-d_1)
  ```

### Greeks
- **Delta**: Sensitivity to changes in the underlying stock price.
- **Gamma**: Rate of change of Delta with respect to the stock price.
- **Vega**: Sensitivity to volatility.
- **Theta**: Sensitivity to the passage of time (time decay).
- **Rho**: Sensitivity to interest rates.

### Implied Volatility
The volatility that equates the market price of an option to the Black-Scholes theoretical price. It is calculated using numerical optimization techniques (e.g., Newton-Raphson).

---

## Applications

1. **Portfolio Risk Management**:
   - Hedge against adverse movements in stock prices or volatility.

2. **Trading Strategies**:
   - Identify opportunities based on implied volatility vs. realized volatility.

3. **Financial Analysis**:
   - Assess risk-adjusted returns and sensitivities for option portfolios.

---

## Limitations
- Assumes constant volatility and risk-free rates.
- Not suitable for American options (requires models like Binomial Trees).
- Ignores dividends in its basic form.

---

## Conclusion
This project demonstrates the practical application of the **Black-Scholes model** and its extensions. It provides a foundation for understanding option pricing, sensitivity analysis, and implied volatility, which are critical for quantitative finance and risk management. While the Black-Scholes model has limitations, it remains a cornerstone of modern financial theory.

---

## Future Work
- Implement pricing for **American options**.
- Extend the model to account for stochastic volatility (e.g., Heston model).
- Include Monte Carlo simulations for pricing complex derivatives.
- Add visualizations for option sensitivity analysis.

---

## Author
Ira Bajpai 
**Contact**: bajpaiira21@gmail.com
**GitHub**: https://github.com/irab21


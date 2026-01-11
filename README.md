# **What is Monte Carlo Simulation?**

Monte Carlo Simulation is a **numerical method** used to model and analyze systems that are affected by **randomness and uncertainty**.

Instead of trying to solve a problem using a single equation, Monte Carlo simulation:

* Generates **thousands or millions of random scenarios**
* Simulates what could happen in each scenario
* Uses **averages of all outcomes** to estimate the true value

In finance, it answers questions like:

> *“What are all the possible future prices of a stock, and what is the expected payoff of a derivative based on them?”*

---

# **Why do we need Monte Carlo Simulation?**

Many real-world financial products depend on **the entire path of prices**, not just the final price.

Examples:

* Barrier options → depend on whether the price ever crossed a level
* Asian options → depend on the average price
* Lookback options → depend on maximum or minimum price

These products **cannot be priced using simple formulas** like Black-Scholes.

Monte Carlo is needed because:

* Markets move randomly
* Prices evolve continuously over time
* Path-dependent contracts need full price trajectories

Monte Carlo lets us **simulate the market** instead of solving it analytically.

---

# **How Monte Carlo Simulation Works**

Monte Carlo follows a very logical process:

1. **Model the randomness**

   Stock prices are assumed to follow:
  <img width="287" height="57" alt="image" src="https://github.com/user-attachments/assets/10fe4970-5e9a-414e-906e-b977037bad3a" />

   which means prices grow with a drift and fluctuate randomly.

2. **Generate random shocks**

   We generate random numbers from a normal distribution:
   <img width="179" height="50" alt="image" src="https://github.com/user-attachments/assets/0871c6ca-e50f-40c7-874a-cc10229438f0" />

   These represent new information hitting the market.

3. **Simulate price paths**

   Using these random numbers, we generate thousands of future price paths:
  <img width="388" height="74" alt="image" src="https://github.com/user-attachments/assets/aef24a3b-9ed7-4e3e-8802-055d02e974a9" />


4. **Apply the payoff rule**

   For each simulated path, we compute the option payoff:

   * For a call: ( \max(S_T-K,0) )
   * For barrier or Asian options: more complex path-based rules

5. **Average and discount**

   The fair price is the discounted average of all payoffs:
   [
   \text{Price} = e^{-rT} \times \text{Average Payoff}
   ]

---

# **What Monte Carlo gives us**

Monte Carlo does not give a single future price.
It gives a **distribution of possible futures**.

From that distribution we can:

* Price derivatives
* Measure risk
* Compute probabilities of events (like barrier hits)
* Estimate Greeks

This is why Monte Carlo is one of the most powerful tools in **quantitative finance**.

---


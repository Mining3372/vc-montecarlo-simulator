# VC Monte Carlo Simulator

![Status](https://img.shields.io/badge/Shiny-Deployed-brightgreen)
![Language](https://img.shields.io/badge/R-ggplot2-blue)
![Monte Carlo](https://img.shields.io/badge/Simulation-1000s%20of%20runs-orange)
![Finance](https://img.shields.io/badge/Domain-Venture%20Capital-purple)

This project simulates venture capital fund performance using Monte Carlo methods to understand the distribution of outcomes for LPs (returns, risk, and payoff shape). It models fund mechanics such as portfolio size, reserves, follow-on strategy, return distributions, and LP cash flow timing.

👉 **Interactive Web App:** https://aryashah.shinyapps.io/vcmontecarlosim/  
👉 **GitHub Repo:** https://github.com/aryashahprog/vc-montecarlo-simulator

---

## Why This Project Exists

Venture capital outcomes are highly **non-linear, power-law driven, and uncertainty-heavy**. Traditional finance tools rarely capture this reality.

This simulator helps VCs, LPs, and fintech analysts build intuition for:

- What the distribution of net LP returns *actually* looks like
- The probability of achieving break-even, 2x, 3x+ outcomes
- How reserve strategy + follow-on policy drive upside
- How the VC J-Curve behaves in practice vs textbooks
- Why fund returns are dominated by tail outcomes

This is about **replacing point estimates with probabilistic thinking**.

---

## Results — TL;DR

> Numbers below are from a $50M simulated fund, ~30 initial deals, 40% reserves, top-quartile follow-ons, and realistic VC multiple distributions.

✅ **Mean Net LP MOIC** ≈ 3.2x  
✅ **Median Net LP MOIC** ≈ 3.0x  
🎯 **Probability of ≥ 3x net fund** ≈ **57%**  
📉 **Left-tail exists, but extreme downside is uncommon**  
📈 **Right-tail dominates outcomes — classic VC behavior**

Key intuition highlights:

- Outcomes are **heavily right-skewed** — a small cluster of exceptional exits drives most upside  
- A meaningful portion of simulated funds cluster around ~2–4x  
- The “dream outcomes” (6–10x funds) exist but are rare  
- Probability of truly poor performance still exists, reinforcing why LP diversification matters

---

## Key Visualizations

### 1️⃣ Net LP MOIC Distribution (Base R)
![MOIC Histogram](images/moic_histogram_base.png)

---

### 2️⃣ Net LP MOIC Distribution + Density Curve (ggplot2)
![Density Plot](images/moic_density_ggplot.png)

---

### 3️⃣ VC Fund J-Curve — LP Net Cash Flows
Median + quantile bands across 1,000 simulated funds.
![J Curve](images/jcurve.png)

---

## Model Design & Assumptions

- Fund size: **$50M**, 10-year life
- ~**30 initial investments**
- **40% reserve ratio** for follow-ons
- Follow-on capital allocated to **top-quartile portfolio companies**
- Exit distribution is **heavy-tailed / power-law influenced**
- Modeled metrics include:
  - Net MOIC
  - Net IRR
  - GP Carry economics
  - Total LP Distributions
- LP-first return modeling

> This isn’t meant to predict an individual fund — it demonstrates the *shape* of VC outcomes.

---

## Tech Stack

- **R**
- **Shiny**
- **ggplot2**
- **dplyr**
- Monte Carlo simulation techniques

---

## ▶️ Run Locally

```r

# Clone
# git clone https://github.com/aryashahprog/vc-montecarlo-simulator.git

# Open project in RStudio

# Install dependencies
install.packages(c("shiny", "ggplot2", "dplyr"))

# Run app
source("shinyapp.R")
shinyApp(ui, server)

---

## Author

Arya Shah  
Georgia Tech — Business Administration (Finance / FinTech)
Fintech • Venture Capital • Data-Driven Investing

Linkedin: linkedin.com/in/aryashahcy

---

If you’d like to collaborate or are interested in VC / FinTech — feel free to reach out!

Disclaimer:
Educational + exploratory only.
Not investment advice.
Not intended to represent any specific fund.

# README — Assignment Part 3

**Course**: 37011 Financial Markets Instruments – Spring 2025  
**Assignment**: Part 3 (Due 11 May 2025)  
**Student**: Maximilien Striebig  

---

## Description

This submission provides solutions to **Assignment Part 3**.  
The notebook applies no-arbitrage principles to European option data, identifies mispriced instruments,  
and designs **static arbitrage strategies** using only the tradables allowed in each task.  

The focus is on:
- **Put–call parity checks**  
- **Vertical spread and butterfly arbitrage** (monotonicity and convexity in strike)  
- **Calendar spread arbitrage** (monotonicity in maturity)  
- **Model-free price bounds** with positive interest rates  

---

## Tasks

### Task 1 — Put/Call Parity (7 marks)

- **Data**: `options1.csv`, European calls and puts, spot price **S₀ = 100**.  
- **Method**: Tested put–call parity for each maturity and strike, inferred discount factors, and detected inconsistency.  
- **Result**: Identified one mispriced option.  
- **Arbitrage strategy**: Constructed synthetic call/put portfolios using parity to lock in a riskless profit.  

---

### Task 2 — Call Price Curves (`options2.csv`) (4 marks)

- **Data**: `options2.csv`, European call options across maturities.  
- **Method**: Plotted call price vs. strike for each maturity. Checked monotonicity and convexity.  
- **Result**: Found violations of no-arbitrage conditions.  
- **Arbitrage strategy**: Built vertical spreads or butterfly spreads to exploit mispricing, generating upfront credit with non-negative payoff.  

---

### Task 3 — Call Price Curves (`options3.csv`) (5 marks)

- **Data**: `options3.csv`, European call options across maturities.  
- **Method**: Similar to Task 2, plus calendar spread checks across maturities at common strikes.  
- **Result**: Detected arbitrage opportunities where call prices decreased with maturity.  
- **Arbitrage strategy**: Constructed calendar spreads to capture riskless profit.  

---

### Task 4 — Mispriced Call with Positive Rates (`options4.csv`) (4 marks)

- **Data**: `options4.csv`, European calls, **S₀ = 150**, no dividends, **r > 0**.  
- **Method**: Verified lower and upper bounds:  
  \[
  \max(0, S_0 - K e^{-rT}) \le C(K,T) \le S_0
  \]  
  and checked monotonicity in strike/maturity.  
- **Result**: Found one mispriced call violating the bounds.  
- **Arbitrage strategy**: Designed a combination of stock, call, and risk-free bond to lock in profit.  

---

## Outputs

- **Plots**: Option price vs. strike curves for each maturity (Tasks 2 and 3).  
- **Logs**: Mispriced options flagged with details of arbitrage strategies.  
- **Notebook**: `STRIEBIG_Maximilien_Assignment_3(2).ipynb` contains the full implementation.  

---

## How to Run

1. Place all `options*.csv` files in the same directory as the notebook.  
2. Open `STRIEBIG_Maximilien_Assignment_3(2).ipynb`.  
3. Run all cells (`Kernel → Restart & Run All`).  
4. Review generated plots and printed arbitrage strategies.  

---

## Dependencies

- Python 3.x  
- pandas  
- numpy  
- scipy  
- matplotlib  

---

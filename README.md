# 25-Year-Natural-Gas-Market-Simulation-MATLAB
Predict **energy demand** and **price trends** over 25 years
## Purpose

- Predict **energy demand** and **price trends** over 25 years.  
- Study impacts of **population growth, income, energy efficiency, climate, and macro shocks**.  
- Provide a **flexible framework** for policy analysis, academic projects, or energy market research.  

---

## Key Assumptions

1. **Population Growth**: Energy demand scales with population. Default ~1% per year.  
2. **Income Growth & Inflation**: Nominal household income grows annually; adjustable.  
3. **Subsidy Reform**: Gradual increase in energy price to account for subsidy removal.  
4. **Behavioral & Insulation Improvements**: Efficiency gains reduce per-household energy consumption.  
5. **Heating Degree Days (HDD)**: Proxy for weather-dependent energy demand; can increase/decrease yearly.  
6. **Macro-Economic Shocks**: Periodic shocks affect income and price to simulate crises or policy changes.  
7. **Supply Constraint**: Energy price responds to demand-supply imbalances via elasticity.  
8. **Structural Demand Growth**: Demand grows annually even without population or price effects.

9. ## Outputs

1. **Energy Demand (units)** — total consumption per year.  
2. **Energy Price (relative unit)** — price including subsidy and shocks.  
3. **Nominal Income** — household income per year.  
4. **Population** — total population per year.

   ## Limitations

- Deterministic model; stochastic weather or energy supply shortages are not included.  
- Does not distinguish between residential, commercial, or industrial energy sectors.  
- Parameter calibration is required for accurate country-specific forecasting.  


Plots are provided for easy visualization.

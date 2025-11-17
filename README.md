## Overview

This model simulates the **demand for natural gas** in the **domestic sector** over a 25-year period, focusing on predicting **energy prices** and **demand** while considering various **economic**, **behavioral**, and **technological** factors. The model utilizes an iterative approach to adjust for policy changes, energy efficiency improvements, demographic trends, and economic shocks.

The key purpose of this model is to forecast the evolution of **natural gas demand** and **prices** in a domestic market context, factoring in population growth, income changes, energy efficiency improvements, government policies, and macroeconomic shocks.

---

## Key Features

### 1. **Demand Segmentation by Household Income**
   - The population is divided into **low-income** and **high-income** households, each with different sensitivities to **price changes**.
   - **Low-income households** are more price-sensitive, so their demand decreases more rapidly when energy prices increase.

### 2. **Energy Efficiency Improvements**
   - Over time, households improve **insulation** and **appliance energy efficiency**, reducing overall energy demand.
   - Insulation improves by 1% annually, and appliance efficiency improves by 1.5% per year.

### 3. **Behavioral Change**
   - As energy prices rise, households change their behavior (e.g., through **smart home adoption**, **thermostat adjustments**, and energy-saving practices).
   - This results in an annual **demand reduction** (modeled as a 0.5% decrease per year).

### 4. **Macroeconomic and Policy Impacts**
   - **Subsidy Removal**: The model simulates a gradual **phasing-out of subsidies** with a 2% annual reduction in subsidy rates.
   - **Carbon Tax**: A carbon tax is introduced after year 10, increasing the price of natural gas to incentivize more sustainable energy use.

### 5. **Heating Degree Days (HDD)**
   - The model adjusts demand based on **heating degree days** (HDD), which varies depending on weather conditions and climate change. Colder winters lead to higher heating demand.

### 6. **Price Adjustments**
   - Energy prices are influenced by inflation, **subsidy reform**, and **carbon taxes**. These price adjustments affect **demand elasticity** and consumer behavior.

### 7. **Population Growth**
   - The model simulates **population growth** at a rate of 1% annually, influencing overall energy demand.

### 8. **Results Visualization**
   - The model generates plots to visualize key outputs:
     - **Income Growth** over time
     - **Energy Demand** growth or reduction
     - **Energy Price** adjustments due to policy reforms
     - **Population Growth** and its impact on demand

---

## Model Assumptions

1. **Inflation**: Household income grows at a rate of **3% per year** due to inflation.
2. **Price Elasticity**: Low-income households are more **price-sensitive** and experience a greater reduction in demand as prices rise.
3. **Energy Efficiency**: Over time, energy efficiency improves with 1% annual increases in insulation efficiency and 1.5% improvement in appliances.
4. **Behavioral Change**: Consumers reduce energy consumption by 0.5% annually due to behavioral changes and adoption of energy-saving technologies.
5. **Subsidy Reform**: A **gradual removal of energy subsidies** occurs at 2% per year.
6. **Carbon Tax**: A **carbon tax** is introduced after year 10, which increases energy prices.
7. **Population Growth**: The population grows at **1% per year**.

---

## Model Outputs

The model generates the following outputs for each year over the 25-year period:

- **Household Income**: Adjusted annually for inflation.
- **Energy Demand**: Calculated by considering energy efficiency improvements, price changes, and population growth.
- **Natural Gas Price**: Adjusted for subsidy reforms, carbon tax, and inflation.
- **Population**: Adjusted annually for population growth.

### Visual Outputs:
- **Income Growth** over time.
- **Energy Demand** changes due to income, efficiency improvements, and price elasticity.
- **Energy Prices** and the impact of **subsidy reform** and **carbon taxes**.
- **Population Growth** and its effect on overall demand.

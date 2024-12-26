# Stochastic Discount Factor Analysis with Hansen-Jagannathan Bound and CRRA Preferences

This Python project explores the relationship between asset pricing and investor preferences by analyzing the **Hansen-Jagannathan Bound (HJ Bound)** and the **Theoretical Stochastic Discount Factor (SDF)** derived from **Constant Relative Risk Aversion (CRRA)** preferences.

##  🔬 Overview

This project implements calculations and visualizations to:

*   **Compute the Hansen-Jagannathan Bound:** This bound defines the minimum volatility required for an SDF to accurately price a set of assets. A high bound indicates that the model needs a volatile SDF to capture risk factors driving asset prices.
*   **Derive the Theoretical SDF from CRRA Preferences:** CRRA preferences are a common way to model investor risk aversion. The formula for the SDF under CRRA preferences links it to consumption growth, reflecting how individuals discount future payoffs based on their risk tolerance.

In simpler terms:

*   The **Hansen-Jagannathan Bound** tells us the minimum "wiggle room" (volatility) a discount factor needs to have to make sense of observed asset prices. If a model's discount factor isn't volatile enough, it can't explain how assets are priced in the market.
*   The **CRRA-based SDF** gives us a theoretical discount factor based on how much people dislike risk and how their consumption changes over time.

## ⚙️ Project Functionalities:

1.  **HJ Bound Calculation:**
    *   Loads historical data on real interest rates, real per capita consumption, and real S&P returns from an Excel file (`data/Shiller_Ch26_data_modified.xlsx`).
    *   Prepares the data by selecting relevant columns, handling missing values, and calculating gross returns and consumption growth.
    *   Implements the formula: σ<sub>m</sub> = sqrt((1 - μ<sub>R</sub>μ<sub>m</sub>)′Σ<sup>-1</sup>(1 - μ<sub>R</sub>μ<sub>m</sub>)) to calculate the HJ Bound for a range of possible mean SDF values (μ<sub>m</sub>).
2.  **CRRA-based SDF Derivation:**
    *   Iterates through different risk aversion coefficients (γ) within a specified range (1 to 40).
    *   For each γ, calculates the CRRA-implied SDF using the formula: *m<sub>t+1</sub> = β(C<sub>t+1</sub>/C<sub>t</sub>)<sup>-γ</sup>*.
    *   Calculates the mean and standard deviation of the CRRA-implied SDF for each risk aversion level.
3.  **Visualization:**
    *   Generates a plot with the HJ Bound as a line and the CRRA-implied SDF as scattered points.
    *   Labels and titles the plot appropriately for better interpretation.

## ⚠️ Assumptions:

*   The project assumes access to the provided Excel file (`data/Shiller_Ch26_data_modified.xlsx`). You might need to change the file path if you use a different data source.
*   Users should have a basic understanding of financial concepts like risk aversion, discounting, and the role of the SDF in asset pricing.

## ️ ✅ Requirements:

*   Python 3.x
*   NumPy: `pip install numpy`
*   Pandas: `pip install pandas`
*   Matplotlib: `pip install matplotlib`

##  🪄 Usage:

*   Clone the Repository:

    ```bash
    git clone https://github.com/MarcosGrossi>/SDF-Analysis-with-Hansen-Jagannathan-Bound.git
    ```


##  Additional Notes

*   This project provides a foundation for exploring the interplay between the HJ Bound, CRRA preferences, and SDFs. You can extend it to analyze different asset classes, explore various risk aversion profiles, or incorporate other asset pricing models.

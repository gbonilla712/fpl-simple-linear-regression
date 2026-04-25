# FPL Correlation Analysis and Simple Linear Regression Models Project

Methodology and Workflow

Analyzing the Relationship Between Weather Variables and Electrical Demand in Florida Power & Light's Service Territory

Prepared by Guillermo Bonilla| April 23, 2026

# 1\. Project Objective

The primary objective of this project is to examine how weather variables influence electrical demand within **Florida Power & Light's (FPL)** service territory. By establishing a statistical relationship or correlation between meteorological factors and power usage, the project seeks to enhance forecasting accuracy and operational planning — particularly in an era marked by shifting climate patterns and growing energy consumption across the state of Florida.

The study employs **simple linear regression models**, working with two variables at a time (one independent and one dependent) to isolate and quantify bivariate relationships. This approach provides a clear, interpretable baseline before advancing to more complex multivariate techniques.

The author's contribution centers on constructing and analyzing simple linear regression models and performing **correlation analysis** between meteorological variables (mean temperature and precipitation) and electrical demand and net generation data across multiple Florida locations and years.

| Core Research QuestionTo what extent do daily weather variables — specifically mean temperature and precipitation — predict daily electrical demand and net generation in FPL's service territory? |
| --- |

# 2\. Data Sources

This study integrates two primary datasets: one capturing electrical demand and generation metrics, and the other capturing meteorological observations across Florida. Both datasets are structured as daily time series, enabling date-aligned bivariate analysis.

## 2.1 Electrical Demand and Net Generation Data

Electrical data was sourced from the **U.S. Energy Information Administration (EIA)** database, specifically focusing on FPL's operational data available through the Real-time Operating Grid portal.

*   **Source:** U.S. Energy Information Administration (EIA) — Real-time Operating Grid
*   **Scope:** Daily time series for FPL's service territory

The dataset comprises the following fields for each recorded day:

| Field | Description |
| --- | --- |
| Datetime | The specific day of measurement |
| Demand (MWh) | Actual electricity consumption per recorded day |
| Forecasted Demand | Predicted load values for comparison with actual demand |
| Net Generation (MWh) | Total electricity generated minus station use, per recorded day |

## 2.2 Meteorological Data

Weather data was sourced from the **Florida State University (FSU) Climate Center**, which captures daily weather information from numerous observation stations across the state of Florida.

*   **Source:** Florida State University (FSU) Climate Center — Downloadable Data
*   **Structure:** Each record is associated with a specific weather station and an observation date, formed by merging separate YEAR, MONTH, and DAY fields into a logical date format

The meteorological dataset includes the following daily measurements:

*   **Precipitation** — measured in inches or millimeters
*   **Maximum Temperature** — daily high temperature
*   **Minimum Temperature** — daily low temperature
*   **Average Daily Temperature** — computed mean temperature (used as the primary independent variable)

## 2.3 Data Coverage

The study encompasses **10 Florida locations** within or adjacent to FPL's service territory, spanning **six years** of daily observations:

| Locations Studied | Years Analyzed |
| --- | --- |
| Ft. Lauderdale, Hialeah, Melbourne, Miami, Daytona Beach, Miami Beach, Vero Beach, Naples, Kissimmee, Ft. Lauderdale Beach | 2019, 2020, 2021, 2022, 2023, 2024 |

For each location and year combination, two dependent variables and two independent variables were defined:

*   **Dependent Variables:**
    *   Y₁ = Daily Electrical Demand (MWh)
    *   Y₂ = Daily Net Generation (MWh)
*   **Independent Variables:**
    *   X₁ = Daily Mean Temperature
    *   X₂ = Daily Precipitation

# 3\. Data Preprocessing

Before conducting any statistical analysis, the raw data from both sources required careful preprocessing to ensure consistency, alignment, and analytical readiness. The following workflow was applied:

1.  **Date Field Unification:** The meteorological dataset stored date information in separate YEAR, MONTH, and DAY columns. These were merged into a single, unified date format to enable temporal alignment with the EIA data.
2.  **Temporal Alignment:** The EIA electrical demand and net generation daily time series was aligned with the FSU meteorological daily observations by matching records on date. This ensured that each day's weather observation was paired with the corresponding day's electrical data.
3.  **Location Matching:** Matched records were ensured between both data sources for each of the 10 Florida locations across each year of analysis (2019–2024).
4.  **Observation Count Variability:** Different locations and years yielded varying sample sizes due to data availability and station reporting gaps. For example:
    *   Kissimmee 2019: 313 observations
    *   Miami 2019: 365 observations
    *   Daytona Beach 2019: 359 observations
    *   Miami 2024: 366 observations
    *   Kissimmee 2024: 330 observations
    *   Hialeah 2024: 324 observations
    *   Ft. Lauderdale 2024: 364 observations
    *   Hialeah 2019 (precipitation model): 332 observations
5.  **Variable Pairing:** Data was filtered and structured for bivariate analysis — pairing one independent variable (mean temperature or precipitation) with one dependent variable (demand or net generation) at a time.

| Note on Sample SizesThe variation in observation counts across locations and years reflects differences in weather station reporting completeness and data availability. Each model's sample size (n) is reported alongside its results to ensure transparency. |
| --- |

# 4\. Correlation Analysis

**Correlation analysis** is a statistical technique used to evaluate the relationship between two variables, helping identify patterns, trends, and the potential for prediction. A correlation exists between two variables when the values of one variable are systematically associated with the values of the other.

## 4.1 Visual Assessment with Scatter Plots

**Scatter plots** serve as the primary visual tool for displaying the relationship between two quantitative variables X and Y. Each data point on a scatter plot represents a single observation, with its position determined by its X and Y values.

A **linear correlation** exists when plotted points can be approximated by a straight line. Two types of linear correlation may be observed:

*   **Positive correlation:** As one variable increases, the other also increases (upward trend from left to right)
*   **Negative correlation:** As one variable increases, the other decreases (downward trend from left to right)

Scatter plots may also include a **trend line** or best-fit line, determined using simple linear regression, to visually represent the direction and strength of the relationship.

## 4.2 Pearson's Correlation Coefficient

**Pearson's Correlation Coefficient (r)** quantifies the strength and direction of the linear relationship between two variables. Its value ranges from −1 to +1:

| Value of r | Interpretation |
| --- | --- |
| r close to +1 | Strong positive linear correlation |
| r close to −1 | Strong negative linear correlation |
| r close to 0 | No linear correlation (variables are not linearly related) |

In this study, Pearson's r was computed for each variable pair to determine whether sufficient linear correlation existed to justify fitting a regression model.

# 5\. Regression Modeling

## 5.1 Simple Linear Regression Model

A **simple linear regression model** predicts a dependent variable Y by fitting a straight line based on a single independent variable X. The model produces a two-dimensional relationship defined by one slope and one intercept. The general form of the regression equation is:

**ŷ = b₁x + b₀**

Where **ŷ** is the predicted value of the dependent variable, **b₁** is the slope (rate of change in Y per unit change in X), and **b₀** is the y-intercept (the predicted value of Y when X equals zero).

## 5.2 Tools and Technology

All statistical analyses were performed using **Microsoft Excel**, leveraging its built-in statistical capabilities:

*   **Analysis ToolPak Add-in:** Used for regression analysis, including generation of regression output tables with coefficients, R², standard error, and significance tests
*   **Pearson Correlation Coefficient Computation:** Used to quantify the linear relationship strength prior to model fitting

## 5.3 Models Constructed

For each of the 10 locations and each year (2019–2024), two primary models were constructed using mean temperature as the independent variable:

*   **Model A:** Daily Electrical Demand (MWh) vs. Daily Mean Temperature
*   **Model B:** Daily Net Generation (MWh) vs. Daily Mean Temperature

Additional models were also constructed testing **daily precipitation** as the independent variable against both dependent variables.

## 5.4 Summary of Top Regression Results

The following table presents the top 12 regression results from the study, representing the strongest linear relationships identified across locations and years. All models use **Daily Mean Temperature** as the independent variable.

| Location | Year | Dependent Variable | n | Pearson r | Regression Equation | R² |
| --- | --- | --- | --- | --- | --- | --- |
| Kissimmee | 2019 | Electrical Demand | 313 | 0.87 | y = 5265.5x − 40031 | 0.7726 |
| Miami | 2019 | Electrical Demand | 365 | 0.88 | y = 7308.3x − 226736 | 0.7772 |
| Daytona Beach | 2019 | Electrical Demand | 359 | 0.87 | y = 5214.4x − 32065 | 0.7627 |
| Miami | 2024 | Electrical Demand | 366 | 0.90 | y = 9911.6x − 382269 | 0.8094 |
| Kissimmee | 2024 | Electrical Demand | 330 | 0.89 | y = 6475x − 83595 | 0.8007 |
| Hialeah | 2024 | Electrical Demand | 324 | 0.89 | y = 8510.3x − 261374 | 0.7918 |
| Kissimmee | 2019 | Net Generation | 313 | 0.87 | y = 4738.3x − 2183.7 | 0.7535 |
| Miami | 2019 | Net Generation | 365 | 0.87 | y = 6520.1x − 161019 | 0.7507 |
| Daytona Beach | 2019 | Net Generation | 359 | 0.86 | y = 4652.3x + 12633 | 0.7364 |
| Miami | 2024 | Net Generation | 366 | 0.88 | y = 9269.8x − 323373 | 0.7798 |
| Kissimmee | 2024 | Net Generation | 330 | 0.88 | y = 6042.2x − 42924 | 0.7669 |
| Ft. Lauderdale | 2024 | Net Generation | 364 | 0.87 | y = 8396.7x − 246755 | 0.7585 |

# 6\. Model Evaluation

## 6.1 R-Squared (Coefficient of Determination)

The **R-squared (R²) value**, also known as the coefficient of determination, measures the goodness of fit of the regression model. It represents the proportion of variance in the dependent variable that is explained by the independent variable.

*   **R² close to 1:** The model is adequate — the independent variable explains a high proportion of the variance in the dependent variable
*   **R² close to 0:** The model is inadequate — the independent variable accounts for very little of the observed variance

For the mean temperature models in this study, R² values ranged from approximately **0.7364 to 0.8094**. This indicates that daily mean temperature explains roughly **73% to 81%** of the variance in electrical demand and net generation across the studied locations and years — a strong result for a single-variable model.

| Key Finding — Mean Temperature ModelsThe highest R² observed was 0.8094 (Miami 2024, Electrical Demand), meaning mean temperature alone explained over 80% of the daily variation in electrical demand. The lowest among the top models was 0.7364 (Daytona Beach 2019, Net Generation), still indicating a strong explanatory relationship. |
| --- |

## 6.2 Precipitation Models — Weak Results

In contrast to the strong results obtained with mean temperature, **precipitation as an independent variable** showed weak positive or negligible linear correlation with both electrical demand and net generation. The following examples illustrate these findings:

| Location | Year | Dependent Variable | n | Pearson r | Regression Equation | R² |
| --- | --- | --- | --- | --- | --- | --- |
| Ft. Lauderdale | 2019 | Electrical Demand | 359 | −0.03 | y = −3612.2x − 351495 | 0.001 |
| Hialeah | 2019 | Net Generation | 332 | 0.08 | y = 9357.1x + 352378 | 0.0065 |

With R² values of **0.001** and **0.0065** respectively, precipitation explains less than 1% of the variance in electrical demand or net generation. These results confirm that **precipitation is not a meaningful standalone predictor** of FPL electrical load in this analytical framework.

# 7\. Interpretation and Conclusions

The analysis across 10 Florida locations and six years of data yields several important findings regarding the relationship between weather variables and FPL's electrical demand and net generation:

1.  **Strong positive linear correlation between mean temperature and electrical demand.** Across all locations and years, higher daily mean temperatures are consistently associated with higher daily electrical consumption. This relationship is statistically significant and robust, with Pearson r values ranging from 0.86 to 0.90 among the top-performing models.
2.  **Strong positive linear correlation between mean temperature and net generation.** The same pattern holds for net generation, confirming that FPL's power output closely tracks temperature-driven demand fluctuations.
3.  **Temperature drives consumption.** Higher temperatures drive higher electrical consumption across all 10 Florida locations, while lower temperatures correspond to reduced consumption. This is consistent with the dominance of air conditioning load in Florida's subtropical climate.
4.  **Urban and coastal population effects.** Cities with higher tourism activity, coastal geography, and larger populations — such as Miami — exhibit stronger positive linear correlations, reflected in higher R² and Pearson coefficient values. Miami 2024 produced the highest R² in the study (0.8094).
5.  **Precipitation is not a significant standalone predictor.** Daily precipitation showed negligible linear correlation with both electrical demand and net generation. R² values for precipitation models were near zero, indicating that rainfall alone does not meaningfully predict electrical load.
6.  **Future direction.** Including additional variables (e.g., humidity, wind speed, day of week, holiday indicators) in a **multiple linear regression model** is expected to increase R² and improve model adequacy. This will be explored in subsequent work.

| Summary of Key ConclusionsMean temperature is a strong, consistent predictor of both electrical demand and net generation across FPL's service territory, explaining 73–81% of daily variance. Precipitation, however, lacks predictive power as a standalone variable. Advancing to multiple regression is the recommended next step to capture additional variance and improve forecasting accuracy. |
| --- |

# 8\. Workflow Summary

The following step-by-step workflow synthesizes the complete analytical process from project conception to final interpretation:

1.  **Define the research objective and scope.** Establish the focus on FPL's service territory and the relationship between weather variables and electrical demand/net generation.
2.  **Acquire electrical demand and net generation data** from the U.S. Energy Information Administration (EIA) Real-time Operating Grid database.
3.  **Acquire meteorological data** from the Florida State University (FSU) Climate Center for 10 Florida locations.
4.  **Preprocess and merge datasets** by unifying date fields and aligning records by date and location.
5.  **Define variable pairs for bivariate analysis.** Dependent variables: electrical demand (MWh) or net generation (MWh). Independent variables: daily mean temperature or daily precipitation.
6.  **Generate scatter plots** to visually assess relationships between each variable pair.
7.  **Compute Pearson's correlation coefficient (r)** for each variable pair to quantify linear relationship strength.
8.  **Fit simple linear regression models** and obtain regression equations (ŷ = b₁x + b₀) for pairs with significant correlation.
9.  **Evaluate model fit using R²** (coefficient of determination) to assess the proportion of variance explained.
10.  **Compare results across locations, years, and variable pairs** to identify patterns and strongest predictors.
11.  **Interpret findings and draw conclusions** about weather-demand relationships in FPL's territory.
12.  **Identify limitations and recommend next steps**, including the transition to multiple linear regression for improved model adequacy.

# 9\. References

1.  Triola, M. F. _Elementary Statistics_, 14th Edition. Chapter 10: Correlation and Regression. Pearson Education.
2.  U.S. Energy Information Administration (EIA). Real-time Operating Grid — FPL Data. Available at: https://www.eia.gov/electricity/gridmonitor/
3.  Florida State University (FSU) Climate Center. Downloadable Data. Available at: https://climatecenter.fsu.edu/climate-data-access-tools/downloadable-data

_FPL Simple Linear Regression Project — Methodology and Workflow | Guillermo Bonilla | April 2026_

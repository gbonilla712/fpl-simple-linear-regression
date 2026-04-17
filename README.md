# fpl-simple-linear-regression

Florida Power & Light (FPL) Simple Linear Regression Analysis
Overview
This project examines how meteorological variables — primarily daily mean temperature and precipitation — influence electrical demand and net generation within Florida Power & Light’s (FPL) service territory. Using simple linear regression models and Pearson correlation analysis, the study evaluates the strength and direction of linear relationships across multiple Florida locations from 2019 to 2024.

The analysis was conducted entirely in Excel, using the built‑in Data Analysis ToolPak for regression modeling and correlation computation.

The primary objective of this study is to examine how weather variables influence the electrical demand within Florida Power & Light’s (FPL) service territory.

Project Structure
Code
fpl-simple-linear-regression/
│── data/
│     ├── eia/                 # Electrical demand & net generation data
│     └── climate/             # Meteorological data from Florida State University (FSU) Climate Center
│── processed data/            # Excel regression outputs, charts, and tables
│── PowerPoint Presentation/   # Report with exported visualizations
│── documentation/             # Methodology notes, data dictionary, workflow
│── README.md
Data Sources
Electrical Demand & Net Generation
U.S. Energy Information Administration (EIA)

Daily time series including:

Actual electrical demand (MWh)

Forecasted demand

Net generation (MWh)

Datetime stamps

The electrical demand data used in this study were sourced from the U.S. Energy Information Administration (EIA) database, focusing on FPL data.

Meteorological Data
Florida State University (FSU) Climate Center

Daily observations, including:

Mean, max, and min temperature

Precipitation

Station‑level geographic coverage

Meteorological observations were obtained from the Florida State University (FSU) Climate Center.

Methodology
The analysis uses simple linear regression, modeling one independent variable at a time:

Dependent Variables (Y)
Daily Electrical Demand

Daily Net Generation

Independent Variables (X)
Daily Mean Temperature

Daily Precipitation

Tools Used
Excel Data Analysis ToolPak

Regression

Pearson correlation coefficient

Scatter plots with trendlines

R² for goodness‑of‑fit evaluation

The technology used was Excel, including the statistical analysis tool packs, in which I used Regression and the Pearson correlation coefficient options.

Statistical Approach
1. Correlation Analysis
Pearson’s correlation coefficient (r) quantifies the strength of a linear relationship.

Interpretation:

r close to 1 → strong positive correlation

r close to -1 → strong negative correlation

r near 0 → no linear correlation

If r is close to 1, there is a strong positive linear correlation… If r is close to 0, there is no linear correlation.

2. Simple Linear Regression
For each city and year, the model:

Y = b_0 + b_1X
Where:

Y = demand or net generation

X = mean temperature or precipitation

b₁ = slope

b₀ = intercept

3. Goodness of Fit
R² measures how well the model explains variation in Y.

Higher R² → better fit.

If the R-squared value is close to 1, the regression model is adequate.

Geographic & Temporal Coverage
Models were created for 10 Florida locations across 2019–2024, including:

Miami

Kissimmee

Hialeah

Ft. Lauderdale

Daytona Beach

Melbourne

Vero Beach

Naples

Miami Beach

Ft. Lauderdale Beach

Simple linear regression models were created… in ten separate Florida locations.

Key Findings
1. Temperature Strongly Predicts Demand and Net Generation
Across all cities and years:

Strong positive correlations (r ≈ 0.86–0.90)

High R² values (≈ 0.75–0.81)

Higher temperatures → higher electrical demand

Lower temperatures → lower electrical demand

Examples from the presentation:

Miami 2024 Demand vs. Mean Temperature:

r = 0.90

R² = 0.8094

Regression: y = 9911.6x – 382269

Kissimmee 2019 Demand vs. Mean Temperature:

r = 0.87

R² = 0.7726

Regression: y = 5265.5x – 40031

The results show a strong positive linear correlation between mean temperature and both electrical demand and net generation.

2. Precipitation Has Weak Predictive Power
Models using precipitation as X showed:

Very weak correlations (r ≈ -0.03 to 0.08)

R² values near zero

Example:

Ft. Lauderdale 2019 Demand vs. Precipitation:

r = -0.03

R² = 0.001

These models overall showed weak positive linear correlation… very weak R-squared values and weak Pearson coefficients.

3. Coastal & High‑Population Cities Show Stronger Relationships
Cities with:

Larger populations

Higher tourism

Coastal climates

…tended to exhibit stronger correlations and higher R² values.

Cities with high tourism, coastal areas, and larger populations exhibit a stronger positive linear correlation.

Conclusions
Mean temperature is a strong predictor of both electrical demand and net generation across FPL’s service territory.

Precipitation is not a meaningful predictor in simple linear regression models.

Simple linear regression provides clear, interpretable insights, but:

Adding more variables (humidity, wind speed, seasonality, holidays, etc.)

Using multivariate regression or machine learning models
…would likely improve predictive accuracy.

Including more variables in the linear regression model will increase the goodness-of-fit indicator, the R-squared coefficient.

Next Steps
Future work may include:

Multiple linear regression

Time‑series forecasting

Feature engineering (heat index, cooling degree days)

Model comparison across years and regions

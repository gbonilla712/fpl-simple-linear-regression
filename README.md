# fpl-simple-linear-regression

⚡ Florida Power & Light (FPL) — Simple Linear Regression Analysis
📘 Overview
This project examines how meteorological variables—primarily daily mean temperature and precipitation—influence electrical demand and net generation within Florida Power & Light’s (FPL) service territory. Using simple linear regression models and Pearson correlation analysis, the study evaluates linear relationships across multiple Florida locations from 2019 to 2024.

The analysis was conducted entirely in Excel using the Data Analysis ToolPak for regression modeling and correlation computation.

🗂️ Project Structure
Code
fpl-simple-linear-regression/
│── data/
│     ├── eia/                 # Electrical demand & net generation data
│     └── climate/             # Meteorological data from FSU Climate Center
│── processed data/            # Excel regression outputs, charts, and tables
│── PowerPoint Presentation/   # Report with exported visualizations
│── documentation/             # Methodology notes, data dictionary, workflow
│── README.md
🌐 Data Sources
Electrical Demand & Net Generation
U.S. Energy Information Administration (EIA)  
Daily time series including:

Actual electrical demand (MWh)

Forecasted demand

Net generation (MWh)

Datetime stamps

The electrical demand data used in this study were sourced from the EIA database, focusing on FPL data.

Meteorological Data
Florida State University (FSU) Climate Center  
Daily observations including:

Mean, max, and min temperature

Precipitation

Station‑level geographic coverage

Meteorological observations were obtained from the FSU Climate Center.

🔧 Methodology
The analysis uses simple linear regression, modeling one independent variable at a time.

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

📊 Statistical Approach
Correlation Analysis
Pearson’s correlation coefficient (r) quantifies the strength of a linear relationship.

Interpretation:

r → 1 → strong positive correlation

r → -1 → strong negative correlation

r → 0 → no linear correlation

Simple Linear Regression
For each city and year, the model is:

Y = b_0 + b_1X
Where:

Y = demand or net generation

X = mean temperature or precipitation

b₁ = slope

b₀ = intercept

Goodness of Fit
R² measures how well the model explains variation in Y.

Higher R² → better fit.

🗺️ Geographic & Temporal Coverage
Models were created for 10 Florida locations across 2019–2024, including:

Miami • Kissimmee • Hialeah • Ft. Lauderdale • Daytona Beach • Melbourne • Vero Beach • Naples • Miami Beach • Ft. Lauderdale Beach

🔍 Key Findings
🌡️ 1. Temperature Strongly Predicts Demand and Net Generation
Across all cities and years:

Strong positive correlations (r ≈ 0.86–0.90)

High R² values (≈ 0.75–0.81)

Higher temperatures → higher electrical demand

Lower temperatures → lower electrical demand

Examples:

Miami 2024 — Demand vs. Mean Temperature

r = 0.90

R² = 0.8094

Regression: y = 9911.6x – 382269

Kissimmee 2019 — Demand vs. Mean Temperature

r = 0.87

R² = 0.7726

Regression: y = 5265.5x – 40031

These results show a strong positive linear correlation between mean temperature and both electrical demand and net generation.

🌧️ 2. Precipitation Has Weak Predictive Power
Models using precipitation as the independent variable showed:

Very weak correlations (r ≈ -0.03 to 0.08)

R² values near zero

Example:

Ft. Lauderdale 2019 — Demand vs. Precipitation

r = -0.03

R² = 0.001

🌴 3. Coastal & High‑Population Cities Show Stronger Relationships
Cities with:

Larger populations

Higher tourism

Coastal climates

…tended to exhibit stronger correlations and higher R² values.

🧾 Conclusions
Mean temperature is a strong predictor of both electrical demand and net generation across FPL’s service territory.

Precipitation is not a meaningful predictor in simple linear regression models.

Simple linear regression provides clear, interpretable insights, but more advanced models would likely improve accuracy.

Adding additional variables—such as humidity, wind speed, seasonality, or holidays—would increase the model’s explanatory power and improve the R‑squared coefficient.

🚀 Next Steps
Future work may include:

Multiple linear regression

Time‑series forecasting

Feature engineering (e.g., heat index, cooling degree days)

Model comparison across years and regions

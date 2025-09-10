# food-production-impact-analysis
# Overview  
Food production significantly affects the environment, contributing to climate change, water scarcity, land degradation, and biodiversity loss. This project analyzes the **environmental footprint of food production** across key metrics:  
- Carbon emissions  
- Water usage  
- Land use  
- Biodiversity loss  

The goal is to uncover patterns, highlight sustainability challenges, and provide **data-driven recommendations** for policymakers, producers, and consumers.  

# Tools  
- **Python (Pandas, NumPy, Matplotlib, Seaborn)** – Data cleaning and visualization.   
- **Power BI / Tableau (optional)** – Dashboards for stakeholder insights.  

# Data Understanding  
The dataset Food_Production.csv contains information on environmental impacts of producing various food products. It has 43 rows (food items) and 23 columns (impact metrics). 

# Key Features 
- Food product – Name of the food item.

- Land use change, Animal Feed, Farm, Processing, Transport, Packaging, Retail – Breakdown of emissions (kgCO₂eq) by production stage.

- Total_emissions – Overall greenhouse gas emissions per food item.

- Eutrophying emissions – Nutrient pollution (gPO₄eq), reported per:
1000 kcal
1 kilogram
100g protein

- Freshwater withdrawals – Water use (liters), reported per:
1000 kcal
1 kilogram
100g protein

- Greenhouse gas emissions – Climate impact (kgCO₂eq), reported per:
1000 kcal
100g protein

- Land use – Agricultural land required (m²), reported per:
1000 kcal
1 kilogram
100g protein

- Scarcity-weighted water use – Adjusted water footprint (liters), reported per:
1 kilogram
100g protein
1000 kcal

# Data Preparation
- Initial Inspection
Checked dataset shape and column names
Displayed first few rows for preview
Used df.info() to examine data types and null counts

- Duplicate Check
Counted duplicate rows with df.duplicated().sum()
No duplicates found

- Missing Value Detection
Counted missing values per column with df.isnull().sum()
Identified rows containing missing values
Created a map linking each food product to the columns where values were missing

- Imputation Strategy
Focused only on numeric columns (excluding the Food product column)
Standardized numeric data with StandardScaler
Applied KNN Imputer (k=5) to estimate missing values based on the closest neighbors
Inverse transformed the data back to its original scale

- Post-Cleaning Validation
Replaced missing values in the original DataFrame
Verified that all missing values were successfully imputed (df.isnull().sum() shows 0)

- Saved the final cleaned dataset as:
food_emissions_imputed.csv



# Analysis

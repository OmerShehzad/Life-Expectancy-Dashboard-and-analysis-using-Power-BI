# Life-Expectancy-Dashboard-and-analysis-using-Power-BI
The project examines the global increase in human lifespan from 1800-2020, highlighting factors such as health, smoking, population density, income, and gender life expectancy, and suggests steps to further improve it.
## Introduction
This project aims to analyze the correlation between population density and life expectancy using Power BI. The analysis leverages data visualization techniques, data cleaning, and advanced DAX expressions to present meaningful insights. The project emphasizes improving life expectancy by addressing healthcare access, social determinants of health, and promoting healthier lifestyles.

## Recommendations for Improving Global Life Expectancy
To improve global life expectancy, a multi-faceted approach is required:
1. **Healthcare Improvement:** Increase healthcare funding, train healthcare professionals, and implement equitable healthcare policies.
2. **Address Social Determinants:** Tackle factors such as income, education, and access to food and clean water.
3. **Control Risk Factors:** Implement policies to reduce tobacco and alcohol consumption.
4. **Promote Healthy Lifestyles:** Encourage physical activity, healthy diets, and discourage risky behaviors.
5. **Invest in Research:** Strengthen data collection and monitoring to improve future policies.

## Project Overview
This project utilizes Power BI for data import, cleaning, modelling, visualization, and analysis. The following steps outline the project structure:

### Section 1: Data Pre-Processing and Loading
1. **Open Power BI.**
2. **Get Data:** Select "Text/CSV" to connect the dataset.
3. **File Selection:** Select the dataset from the local system (326kB CSV file).
4. **Data Preview:** Power BI auto-detects file origin (UTF-8), delimiter (comma), and data types using the first 200 rows.
5. **Load Data:** Select "Load" to ensure successful data import.

### Section 2: Data Cleaning in Power BI
- **Transform Data:** Access Power Query Editor from the "Home" ribbon.
- **Null Values:** Replace empty cells with '0' to ensure data integrity.
- **Data Types:** Correct data types to match column attributes (e.g., whole numbers for primary keys, date format for time columns).

### Section 3: Data Modelling and Normalization
1. **Create Duplicate Table:** Generate a copy of the original data table.
2. **Country Table Creation:**
   - Retain only `Country` and `Status` columns.
   - Remove duplicates.
   - Add an index column renamed as `C-ID`.
3. **Status Table Creation:**
   - Extract the `Status` column as a new query.
   - Remove duplicates.
   - Add an index column for primary key assignment.
4. **Year Table Creation:**
   - Extract the `Year` column as a new query.
   - Remove duplicates.
   - Add an index column for primary key assignment.

### Section 4: Creating the Fact Table
1. **Duplicate Data Table:** Rename as `Data Table`.
2. **Merge Tables:**
   - Merge `Country` and `Year` tables using primary keys.
   - Replace original `Country` and `Year` columns with corresponding keys.
3. **Create Linking Table:**
   - Retain only key columns to establish data relationships.

### Section 5: Dimension Tables
1. **Duplicate Data Table:**
   - Remove unrelated columns.
   - Create multiple dimension tables based on relevant attributes.
2. **Link Dimension Tables:**
   - Establish relationships using primary keys.
   - Set cardinality to "One-to-Many" for accurate data mapping.

### Section 6: DAX Expressions
DAX expressions were used to create calculated measures and custom color scales. One key example is:

```DAX
Life Expectancy Colour Coding For Chart =
SWITCH(
    TRUE(),
    SELECTEDVALUE('Year'[YEAR-NUM]) < SELECTEDVALUE('Extra Year'[Extra year]), "#dddddd",
    [Life Expectancy For Chart] <= 30, "#D64550",
    [Life Expectancy For Chart] <= 45, "#DE6A3E",
    [Life Expectancy For Chart] <= 60, "#E89928",
    [Life Expectancy For Chart] <= 70, "#E89928",
    [Life Expectancy For Chart] <= 80, "#65606A",
    "#474A7D"
)
```

### Section 7: Final Dashboard and Reports
- Interactive visualizations and dashboards were designed to highlight insights on life expectancy patterns.
- Key metrics such as population density, healthcare accessibility, and social determinants were visualized for clear understanding.

## Conclusion
This project provided valuable insights into improving global life expectancy through data visualization and analysis using Power BI. By connecting, importing, and transforming data efficiently, this project demonstrates effective use of Power BI for actionable insights. Continued practice will enhance proficiency in Power BI features like data modelling, calculated tables, dashboards, and report creation, making it an essential tool for data analytics.

## Future Enhancements
- Integrate additional data sources to enhance insights.
- Implement advanced DAX expressions for improved data manipulation.
- Optimize visual design for better storytelling and insight delivery.



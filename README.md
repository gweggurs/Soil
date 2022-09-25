All data required to run the notebooks is available as a zipped folder via Google Drive:
- https://drive.google.com/drive/folders/1tSi-8RoeVKNt2BNSTHtNHD27xPzUxOr7?usp=sharing


7 Notebooks
Python Environments - my environment text file is included and named env_reqs. The environment is my 'base' python kernel with plotly installed--plotly is only required for the 'Soil, Visualization, Add'l EDA' notebook

1. Soil, data acquisition
---
### Warning ###: The Drought section has two api scrapes that will run for 2 - 4 hours total. There is a shorter 'test scrape' that can work as proof-of-concept.
* Book 1 of 7
-Discussing downloaded weather data and formatting it to csv. Scraping a small table from Wikipedia. Pulling Drought data from US Drought Monitor API. Discussing USDA spreadsheet downloaded via self-serve database. 
* Data read: climdiv-tmincy-v1.0.0-20220907.txt, climdiv-tmaxcy-v1.0.0-20220907.txt, climdiv-tmpccy-v1.0.0-20220907.txt, climdiv-pcpncy-v1.0.0-20220907.txt, FIPS_to_ClimDiv.csv, 
* Data written: roughMinTemp.csv, roughMaxTemp.csv, roughAvgTemp.csv, roughPrecip.csv, roughFIPSandClimDiv_df.csv, roughDroughtFIPS.csv
---

2. Soil, Data Wrangling - Weather
---
* Book 2 of 7
-Reformatting 4 sets of weather data and combining them to one dataframe. 
* Data read: roughMinTemp.csv, roughMaxTemp.csv, roughAvgTemp.csv, roughPrecip.csv
* data written: avg_temp.csv, min_temp.csv, max_temp.csv, precip.csv, weather.csv
---

3. Soil, Data Wrangling - Drought 
---
* Book 3 of 7
-Cleaning and reformatting data that was pulled from the US Drought Monitor API. 
* Data read: roughDroughtFIPS.csv, roughDroughtFIPS2.csv
* Data written: drought.csv
---

4. Soil, Data Wrangling part 3: USDA Census of Agriculture 
---
* Book 4 of 7
-Cleaning the last main data source, the Census of Agriculture for 2002, 2007, 2012, and 2017. Also reformatting and merging the three main dataframes. 
* Data read: soil.csv, COA_ChemFertOps&Acres_Counties.csv, roughFIPSandClimDiv_df.csv, coaRough.csv, drought.csv, weather.csv
* Data written: coaRough.csv, drought_full.csv, soilRough.csv
---

5. Soil, EDA 
---
-Additional formatting to include Latitude and Longitude (numeric state+county) and adding Day (numeric date with Year and Month). Exploratory graphing for the numeric columns, additional graphing and analysis for the three types/sources of data. 
* Data read: soilRough.csv, roughFIPSandClimDiv_df.csv,
* Data written: soilFull.csv, soil.csv,
----

6. Soil, Modeling 
---
### Warning ###: Cell #59 in the Gradient Boosting Section is a GridSearchCV and may run for hours
-This notebook contains the predictive (binary classification) modeling and interpretations of results. Models used are Logistic Regression, Decision Tree, Random Forest, and Gradient Boosting.
-The introduction and conclusion are mainly focused on the modeling, but incorporate some background discussed earlier in the project 
* Data read: soil.csv
* Data written: soilmodel.csv, feature_imp_df.csv
---

7.  Soil, Visualization, Add'l EDA 
---
### REQUIRES PLOTLY ###
-This notebook contains a summary of the previous EDA, the modling insights and the four main points of the project.
A high fidelity visualization was set up in plotly for each point.
* Data read: soil.csv, feature_imp_df.csv
* Data written: none
---

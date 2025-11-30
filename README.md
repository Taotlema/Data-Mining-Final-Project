# U.S. Domestic Commodity Flow Analysis
This repository and its contributions have been dedicated to the Final Project of ITCS 3162: Data Mining Course at UNC-Charlotte. 

## Introduction

Throughout the Fall 2025 semester, the team behiend this project has been tasked with learning and implementing data mining techniques. Using a range of algorithms and machine learning to uncover patterns, trends, and useful information from data. Oftentimes applying these systems to specific senarios involing finance, commerce or transits; fields which greatly benefit from data analysis. As we embark creating on one last course application we've delegated to uncover as much meaningful insight from domestic commodity exhanges across the United States. Leveraging this ample playground of information to try and apply the majority of the learning competencies from our course.

### About Our Data

Our team will conduct our data mining investigation using the **2017 Commodity Flow Survey Database** provided by the **U.S. Census Bureau**. Commodities in this case would be best defined as typically raw and minimally processed materials or anything that wouldn't be a product or reasource sold directly to a consumer. An example would lumber, grain, or even machine parts. Using this provided database would play a pivotal role in storytelling about the realities of these exchanges. Below is a link to the website where we accessed our dataset and infromation. 

**Access Link:** https://www.census.gov/data/datasets/2017/econ/cfs/historical-datasets.html

As mentioned, this databased contained a myriad of infomation needed to put together the exact realities of commodity exchanges across the United States. Which, can be very confusing for those unfammiliar with this kind of data. So below are tables showing relevant fields, and how we factored these into our project.
- - -
**Data Variables:** Index of fields attached to each commodity exchange.  

| Field | Descirption |
|--------|----------|
| **SHIPMT_ID** | Shipment identifier |
| **ORIG_STATE** | FIPS state code of shipment origin |
| **ORIG_MA** | Metropolitan area of shipment origin |
| **ORIG_CFS_AREA** | CFS Area of shipment origin|
| **DEST_STATE** | FIPS state code of shipment destination |
| **DEST_MA** | Metropolitan area of shipment destination |
| **DEST_CFS_AREA** | CFS Area of shipment destination |
| **NAICS** | Industry classification of shipper |
| **QUARTER**| Quarter of 2017 in which the shipment occurred |
| **SCTG**| 2-digit SCTG commodity code of the shipment |
| **MODE** | Mode of transportation of the shipment |
| **SHIPMT_VALUE** | Value of the shipment in dollars |
| **SHIPMT_WGHT**| Weight of the shipment in pounds |
| **SHMPT_DIST_GC** | Great circle distance between shipment origin and destination (in miles) |
| **SHMPT_DIST_ROUTED** | Routed distance between shipment origin and destination (in miles) |
| **TEMP_CNTL_YN** | Temperature controlled shipment - Yes or No |
| **EXPORT_YN** | Export shipment - Yes or No |
| **EXPORT_CNTRY** | Export final destination - International Regions |
| **HAZMAT** | Hazardous material (HAZMAT) code |
| **WGT_FACTOR** | Shipment tabulation weighting factor. |
- - -
**CFS Areas:** These are effectively the area identifying codes, used to highlight where a commodity orginated from and it s being exported towards. For our project when mining we made the distinction of filtering out data for North Carolina speicifcally, or used Natioanl Data.

| Metro Area Code | State Code | Location |
|--------|----------|----------|
| 172 | 37 | Charlotte-Concord |
| 268 | 37 | Greensboro--Winston-Salem--High Point |
| 450 | 37 | Raleigh-Durham-Chapel Hill |
| 99999 | 37 | Remainder of North Carolina |

### Our Methodology

Our approach to mining this data would rely on applying four of the techniques {**Data Visualization**, **Classification**, **Regression**, and **Clustering**} learned in our data mining class. We would then leverage these techniques for investigations on either a North Carolinian, or National basis. Using each system to generate insight on the commodity data, while also assessing the utility and efficency of each data mining process. We will be asking and answering the questions, of how can we apply these techiniques within this given context and how useful is it to do so.

## Initial Data Investigation

### Visualizing: National Trends

<img width="853" height="456" alt="image" src="https://github.com/user-attachments/assets/92b092a5-7813-46d4-8f15-57aa0a9ff15c" />

To better understand out data, we wanted to first investigate what the data could tell us about the national trends. Our first visualization looks at which states contributed the most to outbound commodity shipment value, and based on the dataset's FIPS codes, the top three were South Carolina, Texas, and Washington. These states being at the top highlight how the outbound commodity movement is much higher in these areas, and less distributed in other areas in the country. Outbound commodity is much more concentrated in these states where there is more high-voume export infrastructure, and signifies a large industrial/agriciultural output. These results show how these states play a much larger role in driving national commodity flow than others, which can be attributed to factors such as strong machinery production, the massive energy sectors in Texas, and the international port activity in Washington.

<img width="720" height="541" alt="image" src="https://github.com/user-attachments/assets/1ceeaf56-0679-4ea8-ac4a-56b3c9a170c3" />

In our second visualization we looked at how commidities were transported across the U.S., and learned that the top three modes by far were 4 (For-hire truck), 5 (Company-owned truck), and 14 (Parcel/USPS/Courier), which drastically dominated the shipment activity across other modes. This distribution aligns with the structure of the U.S. freight system, where trucking remains one of the more important and popular modes of transporting. For-hire and company-owned trucking together accounted for the vast majority of freight movement, which aligns with the country's extensive highway system and dependency. The prominence of parcel/USPS/courier reveals the growing nationwide demand for e-commerce activity and smaller shipments as well. Other modes such as rail, air, and water were far less frequent, indicating that they perhaps serve more industry specific roles, but overall the distribution reveals how central trucking is in the flow of commodities.

<img width="866" height="542" alt="image" src="https://github.com/user-attachments/assets/58f31572-561e-45ef-8290-31c38c26596c" />

For the third visualization, we looked at the shipment distance distribution. The histogram reveals that a big majority of most shipment fall within shorter distance ranges, which could suggest a strong reliance on regional transport opposed to traveling longer distances. This reflects how many materials and goods are usually sourced and consumed within the same generla region to minimize transportation time and costs. However, there is still presence of long-distance transportation, which signifies that there are some industries that rely on across regional distribution. This spread of distribution provides useful context in analyzing transportation mode choices such as why trucking is much more prevalent, which aligns with how most shipment is within a drivable distance.

<img width="866" height="542" alt="image" src="https://github.com/user-attachments/assets/46558479-e8e0-4daa-97ed-d6c6fbf6ea92" />

For our final visualization of national trends, we wanted to understand what was actually being moved, and visualized the more frequenty occuring commodity categories by SCTG (Standard Classification of Transported Goods) code. The chart reveals that the top three most transported goods were codes 43, 35, and 40, which corresponded to mixed freight, electronic and other electrical equipment and components, and miscellaneous manufactured products. These results reveal how much of the freight system could be driven by high-volume and manufacturing related good. Mixed freight goods can reflect multiple types of foods togetherm which can signify the common logistical practices in trucking and parcel shipping. The large amount of electronic goods being moved also signifies a nationwide demand for such products. The prevalence of miscellaneous goods being moved also signals a large demand for varying manufactured goods. Overall, these top categories reveal that the national commodity flow in the U.S. is shaped heavily by mixed loads, electronics, and general manufactured goods.


### Visualizing: NC Trends

## Classification Investigation

### Classifcation: National Trends

### Classification: NC Trends

## Regression Investigation 

Regression is a supervised machine learning method that parses through labeled data to analyze relationships between the dependedna and independent variables within a given dataset. Not only is Regression great for uncovering relationships between different fields, but it also is great for predict outcomes, forecasting, and detecting outliers in the data. With what we know about this data mining technnique, we can quickly identify several opportunities for to use this method in evaluating the commodity flow dataset.

Given what we know about how regression is typically implemented, the goals of our investigation is two-fold:
- **Identify which features have the strongest relationship with shipment value.**
- **Evaluate how well we can predict shipment value using different engineered inputs.**

**Initial Exploration and Correlation Analysis**
To prepare for regression modeling, we began by exploring relationships across all fields in the dataset through a correlation heatmap. Because the dataset contains a mix of categorical, binary, and numerical variables, several fields were encoded or mapped to ensure they could be meaningfully compared.  

The resulting heatmap provided early insight into which variables carried the strongest linear relationships with one another. As expected, we observed relatively low correlation between most variables and shipment value, which previewed the challenges of building strong predictive models on this dataset.

<img width="720" height="541" alt="image" src="https://github.com/Taotlema/Data-Mining-Final-Project/blob/main/Output%20Files/Regression/output_7_0.png?raw=true" />


**Visualizing Shipment Value by Commodity Category**  

To further understand how the target variable behaved across the dataset, we generated a boxplot breaking down shipment value by SCTG commodity code. This visualization revealed that certain categories contain extreme high-value outliers—likely representing unusually large or specialized shipments—while most remain tightly concentrated near lower shipment values.

This distribution confirms that the dataset has heavy tails, which complicates prediction and contributes to the high RMSE observed later.

<img width="720" height="541" alt="image" src="https://github.com/Taotlema/Data-Mining-Final-Project/blob/main/Output%20Files/Regression/output_9_0.png?raw=true" />

**Feature Engineering and Preparation**  

Before training our regression models, we engineered several new features to bring more structure and signal into the dataset:
- TEMP_CNTL, EXPORT, HAZ – converted operational flags into binary features
- DIST_RATIO – ratio of routed to straight-line distance, indicating route complexity
- VALUE_PER_LB – shipment value normalized by weight
- Standard numerical fields such as weight, distance, commodity code, and NAICS were preserved as core predictors

We then used SelectKBest with an F-test scoring function to automatically identify the top 8 most predictive features. These included:
- SHIPMT_WGHT (strongest predictor by far)
- EXPORT
- VALUE_PER_LB
- DIST_RATIO
- TEMP_CNTL
- SHIPMT_DIST_ROUTED
- HAZ
- SCTG
This selection process helped narrow the focus to features with meaningful influence over shipment value.

**Regression Models and Evaluation**

We developed and tested two regression models using identical preprocessing pipelines:
- Linear Regression
- Ridge Regression (with regularization parameter alpha = 5.0)
Both pipelines included imputation, scaling, feature selection, and model fitting. We trained using an 80/20 train–test split.

**Model Performance**
Across both runs of our experiments, the models performed nearly identically. While they were not strong predictors, they provided meaningful insight into the complexity and variability of shipment value in commodity flow data.  

Key metrics included:
- R² ≈ 0.08 : the models explain roughly 8% of the variance
- Test RMSE ≈ $275,000 : reflecting extreme outliers and heavy-tailed distributions
- MAE ≈ $19,500 : average error across predictions
- Training R² ≈ 0.004 : showing almost no learnable linear structure in training data

Ridge regularization made almost no difference, indicating that overfitting was not a significant issue in the first place—the dataset is simply noisy and lacks strong linear relationships between features and shipment value.

<img width="720" height="541" alt="image" src="https://github.com/Taotlema/Data-Mining-Final-Project/blob/main/Output%20Files/Regression/output_19_1.png?raw=true" />


Although our models did not produce strong predictive power, the regression investigation still proved valuable in revealing how different factors influence shipment value. We found that physical characteristics; particularly shipment weight and value density—played the most significant role, while operational flags such as export status and temperature control had smaller but still measurable effects. The limited R² scores suggested that linear methods can only capture a small portion of the variability in shipment value, likely due to the complexity of freight pricing and other factors not represented in the dataset. Ultimately, **regression served less as a forecasting tool and more as a diagnostic technique**, helping us identify which features meaningfully contribute to shipment value and where the data lacks strong linear relationships.

## Clustering Investigation

### Clustering: National Trends

### Clustering: NC Trends

## Grand Overview

## Contributors

### Ayemhenre Isikhuemhen
**Computer Science Student** at University of North Carolina at Charlotte | Class of 2026<br>
Contacts: aisikhue@charlotte.edu | github.com/Taotlema
### Madison Roberts
**Computer Science Student** at University of North Carolina at Charlotte | Class of 2026<br>
Contacts: mrobe142@charlotte.edu | github.com/madieroberts

## References
1) Python Software Foundation. (2023). Python 3.x. Retrieved from https://www.python.org/
2) McKinney, W. (2023). pandas: Python Data Analysis Library. Retrieved from https://pandas.pydata.org/
3) Hunter, J. D. (2007). Matplotlib: A 2D graphics environment. Computing in Science & Engineering, 9(3), 90-95.
4) Waskom, M. L. (2021). seaborn: statistical data visualization. Journal of Open Source Software, 6(60), 3021.
5) U.S. Census Bureau. (2017). Commodity Flow Survey: Historical Datasets. Retrieved from https://www.census.gov/data/datasets/2017/econ/cfs/historical-datasets.html

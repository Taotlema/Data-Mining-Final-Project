# U.S. Domestic Commodity Flow Analysis
This repository and its contributions have been dedicated to the Final Project of ITCS 3162: Data Mining Course at UNC-Charlotte. 

## Introduction

Throughout the Fall 2025 semester, the team behind this project has been tasked with learning and implementing data mining techniques, using a range of algorithms and machine learning tools to uncover patterns, trends, and useful information from data. These systems are often applied to scenarios involving finance, commerce, or transit; fields that greatly benefit from data analysis. As we embark on creating one last course application, we’ve been tasked with uncovering meaningful insights from domestic commodity exchanges across the United States, leveraging this ample playground of information to apply the majority of the learning competencies from our course.

### About Our Data

Our team conducted our data mining investigation using the **2017 Commodity Flow Survey Database** provided by the **U.S. Census Bureau**. Commodities in this context are best defined as raw or minimally processed materials—anything that wouldn't typically be a finished product or resource sold directly to a consumer. Examples include lumber, grain, or machine parts. This database played a pivotal role in telling the story behind these exchanges. Below is a link to the website where we accessed our dataset and supporting information.

**Access Link:** https://www.census.gov/data/datasets/2017/econ/cfs/historical-datasets.html

As mentioned, this database contains a wide range of information needed to understand the realities of commodity exchanges across the United States, which can be confusing for those unfamiliar with this type of data. Below are tables showing relevant fields and how we factored them into our project.
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
**CFS Areas:** These are the area identifying codes used to highlight where a commodity originated from and where it was shipped to. For our project, we made the distinction of filtering out data for North Carolina specifically or using national data.

| Metro Area Code | State Code | Location |
|--------|----------|----------|
| 172 | 37 | Charlotte-Concord |
| 268 | 37 | Greensboro--Winston-Salem--High Point |
| 450 | 37 | Raleigh-Durham-Chapel Hill |
| 99999 | 37 | Remainder of North Carolina |

### Our Methodology

Our approach to mining this data relies on applying four of the techniques learned in our data mining class: **Data Visualization**, **Classification**, **Regression**, and **Clustering**. We leveraged these techniques to investigate the data on either a North Carolina–specific or national basis. Each system helped us generate insight into the commodity data while also allowing us to assess the utility and efficiency of each data mining process. We sought to ask and answer the questions: How can we apply these techniques within this context, and how useful is it to do so?

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

For my part of the project, I focused on classification at the national level. Earlier in the analysis we saw that three transportation modes dominate U.S. shipment activity: for-hire truck (4), company-owned truck (5), and parcel/USPS/courier (14). So instead of trying to predict every possible mode, I built a classification model to distinguish only between these three. The primary goal was to see how well a model could recognize patterns in the commodity flow data and predict how a shipment is likely to move.

#### Preprocessing and Feature Engineering

Before training, I had to clean and restructure the dataset. A lot of the fields needed to be converted into something a model could actually work with.

#### Filtering to the three major modes

Once I filtered down to MODE 4, 5, and 14, the dataset went from 213k rows to 204,902 rows, with the following counts:

- 83,602 shipments → MODE 4  
- 65,119 shipments → MODE 5  
- 56,181 shipments → MODE 14  

This lines up with our earlier visualizations showing trucking dominating national freight.

#### Encoding all the categorical fields

Several columns weren’t numeric, so I encoded them:

- **SCTG codes** were mapped to a numerical index (`SCTG_indexed`) and the original SCTG column was removed.  
- **EXPORT_CNTRY** was one-hot encoded, which created individual columns for each export region.  
- **HAZMAT** was also one-hot encoded to capture the different hazard classes.  
- **TEMP_CNTL_YN** and **EXPORT_YN** were mapped from 'Y'/'N' to 1/0, with missing values defaulting to 0.  

After all this, the feature matrix ended up with 24 columns total.

#### Handling missing values

The only column with missing values was `WGT_FACTOR`.  
I filled missing values using the mean within each split (train, dev, test), which avoids data leakage.

#### Train / Dev / Test Splits

I created two splits:

##### Train–test split  
- 10,000 rows used for the test set  
- The rest for training (stratified by MODE)

##### Train–dev split  
- Took another 10,000 rows out of the training set for development/validation

The final counts were:

- **Training:** ~184,902 rows  
- **Development:** 10,000 rows  
- **Testing:** 10,000 rows  

This setup gave me room to train models and evaluate them honestly without touching the test set.

---

#### Models and Results

I tested two models: **Logistic Regression** and a **Decision Tree**. I mainly wanted to compare how a linear model vs. a non-linear model handled this mix of encoded and numeric features.

#### Logistic Regression

- `solver='liblinear'`  
- `max_iter=10000`  

**Development Accuracy:** 0.7157

| Mode | Precision | Recall | F1 |
|------|-----------|--------|----|
| 4 | 0.76 | 0.63 | 0.69 |
| 5 | 0.62 | 0.72 | 0.67 |
| 14 | 0.78 | 0.84 | 0.81 |

Logistic Regression picked up on some of the differences between the modes, but it struggled the most with MODE 4 vs MODE 5. That makes sense because the two trucking modes are inherently similar in weight, value, and distance profiles.

#### Decision Tree Classifier

- `random_state=42`  
- No other tuning  

**Development Accuracy:** 0.7292

| Mode | Precision | Recall | F1 |
|------|-----------|--------|----|
| 4 | 0.71 | 0.73 | 0.72 |
| 5 | 0.70 | 0.70 | 0.70 |
| 14 | 0.79 | 0.77 | 0.78 |

The Decision Tree performed slightly better overall and produced more balanced scores. Since it can capture interactions between variables, it handled the subtleties between different shipment types better than Logistic Regression.

---

#### Insights and Interpretation

Even though the models are far from perfect, they still reveal useful information about national shipment behavior:

- **Trucking really dominates**, and the models reflect that. Both MODE 4 and MODE 5 show up constantly, which makes it harder for any model to cleanly separate them.  
- **Parcel shipments stand out the most.** MODE 14 consistently has the strongest metrics because these shipments tend to be lighter and behave differently than bulk freight.  
- **Company-owned vs. for-hire trucking is the hardest distinction.** Their feature distributions overlap almost entirely. Without deeper operational data, it makes sense that the models confuse them.  
- **Non-linear relationships matter.** The Decision Tree’s improvement shows that mode choice isn’t a simple linear problem.  

Overall, classification helped us understand how shipments “cluster” around transportation modes, even if the models aren’t meant to be perfect predictors.

---

#### Impact and Considerations

If a system like this were used in a real logistics environment, it could influence:

- **Infrastructure planning** — which regions are relying most heavily on trucking or parcel networks  
- **Sustainability efforts** — spotting opportunities for shifting freight to cleaner modes  
- **Operational decision-making** — anticipating how shipments are likely to move  

At the same time, there are limitations:

- We don’t have cost structures, deadlines, or carrier constraints, all of which heavily influence mode selection.  
- A model trained on historical patterns could reinforce existing inefficiencies.  
- Misclassification in the real world could lead to planning mistakes or uneven distribution of freight traffic.  

Because of this, classification in this context is best used as a **pattern-finding tool**, not for automated routing decisions.


### Classification: NC Trends

For this part of the question we built a Binary classification model to answer the question “Can we predict whether a shipment from North Carolina will be exported (EXPORT_YN) based on commodity type (SCTG), transportation mode, weight, and distance?”.  The preprocessing for this was creating a new Dataset of only the NC values, and dropped the Export boolean column.  We then applied hot encoding for categorical variables and scaling for numeric variables, and the model was tried using a 75/25 train–test split.  With this processing the model was able to distinguish between domestic and export shipments.  Overall, the model demonstrated that features like transportation mode, commodity classification, and travel distance play meaningful roles in predicting whether a shipment is exported, providing useful insight into North Carolina shipping patterns.


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

<img width="720" alt="Clustering Table" src="Output%20Files/Clustering/clustermodel.png" />


To describe my data mining process for this clustering model first I will describe what this model is. This is a comparative K-means clustering model that uses several values of k. This model is meant to calculate inertia and silhouette scores for each tested k value to evaluate the cluster quality. The reason why I am made this model is to discover any patterns in export shipments, I also wanted to determine with the clustering model how shipments group together based on export status, destination country, value, and weight. How I made this clustering model is by first making EXPORT_YN and EXPORT_CNTRY numerical categories, then I made a table with important factors for analying the exporting. After that I scaled the selected features and compared multiple K values, lastly I made the compared multiple K values results visual. 

**Cluster Plot Graphs**

Elbow method plot of the k-means clustering: 
- Lower inertia = more compact clusters
- Higher inertia = clusters are less compact 

The Elbow method plot of the k-means clustering shows how compact the clusters are for each k and helps identify the point where adding more clusters stops improving the model.

silhouette score by number of clusters plot graph: 
- Closer to 1 = cleanly separated clusters
- Around 0 = overlapping clusters
- Negative = bad clustering

While the silhouette score by number of clusters plot graph shows how well-separated and well-defined the clusters are for each k and helps confirm the quality of cluster formation.

<img width="720" alt="Elbow method plot graph" src="Output%20Files/Clustering/output_elbow.png" />
<img width="720" alt="Silhouette Score Plot graph" src="Output%20Files/Clustering/output_SS.png" />


### Clustering: NC Trends
<img width="720" alt="PCA graph" src="Output%20Files/Clustering/PCA.png" />
<img width="720" alt="Elbow method plot graph" src="Output%20Files/Clustering/Elbow method.png" />
<img width="720" alt="Box plot evaluation" src="Output%20Files/Clustering/Box Plot Evaluation.png" />
<img width="720" alt="Pairplot evaluation" src="Output%20Files/Clustering/Pairplot Evaluation.png" />

## Grand Overview

## Contributors

### Ayemhenre Isikhuemhen
**Computer Science Student** at University of North Carolina at Charlotte | Class of 2026<br>
Contacts: aisikhue@charlotte.edu | github.com/Taotlema
### Madison Roberts
**Computer Science Student** at University of North Carolina at Charlotte | Class of 2026<br>
Contacts: mrobe142@charlotte.edu | github.com/madieroberts
### Jesse Schefers
**Computer Science Student** at University of North Carolina at Charlotte | Class of 2026<br>
Contacts: jschefer@charlotte.edu | github.com/jess11233
### Nash Balakrishna
**Data Science Major and Computer Science Minor** at University of North Carolina at Charlotte | Class of 2026<br>
Contacts: nbalakr2@charlotte.edu | github.com/nbalakr2
### Kristen Lai
**Computer Science Student** at University of North Carolina at Charlotte | Class of 2028<br>
Contacts: klai3@charlotte.edu | github.com/kristenlai
### Kristen Lai
**Computer Science Student** at University of North Carolina at Charlotte | Class of 2026<br>
Contacts: nto@charlotte.edu | github.com/nathanto99

## References
1) Python Software Foundation. (2023). Python 3.x. Retrieved from https://www.python.org/
2) McKinney, W. (2023). pandas: Python Data Analysis Library. Retrieved from https://pandas.pydata.org/
3) Hunter, J. D. (2007). Matplotlib: A 2D graphics environment. Computing in Science & Engineering, 9(3), 90-95.
4) Waskom, M. L. (2021). seaborn: statistical data visualization. Journal of Open Source Software, 6(60), 3021.
5) U.S. Census Bureau. (2017). Commodity Flow Survey: Historical Datasets. Retrieved from https://www.census.gov/data/datasets/2017/econ/cfs/historical-datasets.html

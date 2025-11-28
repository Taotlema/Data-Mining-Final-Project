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

Our approach to mining this data would rely on applying four of the techniques {Data Visualization, Classification, Regression, and Clustering}; learned in our data mining class. We would then leverage these techniques for investigations on either a North Carolinian, or National basis. Using each system to generate insight on the commodity data, while also assessing the utility and efficency of each data mining process. We will be asking and answering the questions, of how can we apply these techiniques within this given context and how useful is it to do so.

## Initial Data Investigation

### Visualizing: National Trends

### Visualizing: NC Trends

## Classification Investigation

### Classifcation: National Trends

### Classification: NC Trends

## Regression Investigation 

## Clustering Investigation

### Clustering: National Trends

### Clustering: NC Trends

## Grand Overview

## Contributors

### Ayemhenre Isikhuemhen
**Computer Science Student** at University of North Carolina at Charlotte | Class of 2026<br>
Contacts: aisikhue@charlotte.edu | github.com/Taotlema

## References

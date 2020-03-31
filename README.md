

## OJECTIVE:-

To perform any reformatting/wrangling, checking and cleaning on the coral bleaching data for 8 sites in the Great Barrier Reef for different kinds of corals over last 8 years in order to determine the worst coral bleaching and how the location affects bleaching on different kinds of coral by supporting reasons with the help of data exploration using Tableau visualizations.  

## 1. INTRODUCTION

The following report explains the transforming of data for a valuable purpose such as data analytics, which uses visual exploration to describe the characteristics of the dataset. The goal of the report is to visualize the data to determine answer the questions to be followed in the data exploration section of this report. 

The dataset consists of eight sites in the Great Barrier Reef and gives the percentage of bleaching for different coral types namely: hard corals, soft corals, sea pens, sea fans and blue corals respectively over a period of 8 years from 2010 to 2017. 

## 2. Data WRANGLING

### Challenges with original dataset (Data Structure):

#### i) The data is not represented as individual observations and attributes:
This original data set violates the principles of tidy data (Wickham, 2014) i.e., from a single observation it is difficult to describe the characteristics of each coral type and the percentage of bleaching for any given year. As shown in the figure1.1 the observations for site01 displays the characteristics for both corals and sea fans as a result it will be difficult to visualize them as separate data in Tableau Public.

Hence, for accuracy of statistical analysis it is necessary to visualize dataset into a standard format of rows and columns.

![](Images/Raw%20Data1.png)
### Figure 2.1

#### ii)  Column headers are values, not variable names:
the variables 2017, 2016, 2015 etc. form both the rows and column as shown in figure2.2 and similarly with coral types: soft corals, sea fans etc. Thus, the representation and visualization of this data can make the computation difficult

![](Images/Raw%20Data2.png)
### Figure 2.2

To better reflect the roles of 2017, 2016 etc. and each coral type in the dataset, the variable column is renamed to ‘Year’ and ‘Types of Coral’ respectively as shown in figure2.3. Hence, representing in this format determines each dataset unit as a combination of % of bleaching and Type of Coral.

![](Images/Raw%20Data3.png)
### Figure 2.3

#### iii) Long format over wide format:
Figure2.2 represents the wide format of the dataset and figure2.3 represents the long format respectively. In the long format when the occasion (Year in this case) is the unit of analysis, we can use each Year’s ‘Site Name’ as a covariate for same Year’s % of bleaching value. In the wide format, when the unit of observation is ‘Site Name’, there is no way to do this. This implies we can use any of the Site Names as covariates for all years, but not Year-specific covariates.


## 3. CLEANING INCORRECT DATA

### 3.1 Identifying the Outliers:

The two outlier (% of bleaching) identified within the given data is shown below in figure3.1 which is represented by a line graph and box plot of the data to spot the outliers visually. The outliers can thus skew the interpretation of the data. The 

![](Images/Outliers.PNG)
The outliers in this case are not ignored and are corrected to ensure that the data interpretation is as accurate as possible, with an assumption that the decimal point placement was captured incorrectly within the dataset. The outliers were corrected to ‘46.96%’ (two decimal points) for Site07 blue corals (2013) and ‘14.88%’ (one decimal point) for Site08 hard corals (2014). The after transformation of outliers is as shown below in the figure 3.2. 

![](Images/Outliers1.PNG)

### 3.2 Null values:
The null values (% of bleaching) contribute to 30% of the total values (% of bleaching). The null values can mean a zero value or an error in capturing the values. This case ignores the null values and does not consider these null values into statistical analysis of the data exploration. 

### 3.3 Correction of latitude coordinate: 
The dataset also includes the longitude and latitude coordinates of the Great Barrier reef which is located off the coast of Queensland in northeastern Australia (Claudino-Sales, 2019). The coordinates given in the original dataset when plotted across the symbol map on Tableau Public, points the ‘Site02’ location far away from northeastern coast as shown in the figure3.3(a). On observing the coordinates provided in the original data shows that there is a manipulation of sign in the latitude value of ‘Site02’ as shown in figure3.3(b). 

To fix this error the sign is changed to negative for the latitude coordinates of ‘Site02’ and re-plotted to map the exact location of Great Barrier Reef as shown in figure3.3(c) in the world map. 

![](Images/Latitude%20Error.png)
![](Images/Latitude%20Corrected.png)


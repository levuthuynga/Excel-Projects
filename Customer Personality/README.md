# Customer Personality Analysis

This is my analysis process. I did it basically in Excel. This project is my first time doing clustering, trying to find more about customer behaviours and optimize marketing plans of this unreal company, than just a descriptive analysis and some general insights.

### [EXCEL FILE](https://github.com/levuthuynga/Excel-Projects/blob/main/Customer%20Personality/Customer%20Personality%20.xlsx)

Here are 4 steps of this analysis:
1. Ask
2. Prepare
3. Process
4. Analyze
 
*As in Excel file, the sheet order should be: Desciptive Analysis to get general ideal about data, then clean data in Data V2, analyze data in Pivot, create customer clusters in Divide into group, then analyze customer clusters in Cluster Demography and Cluster Behaviours. The conclusion will be in Conclusion sheet.*

## Context
Customer Personality Analysis is a detailed analysis of a company’s ideal customers. It helps a business to better understand its customers and makes it easier for them to modify products according to the specific needs, behaviors and concerns of different types of customers.

Customer personality analysis helps a business to modify its product based on its target customers from different types of customer segments. For example, instead of spending money to market a new product to every customer in the company’s database, a company can analyze which customer segment is most likely to buy the product and then market the product only on that particular segment.

[DATASET](https://www.kaggle.com/imakash3011/customer-personality-analysis)

## I. Ask

Analysis goal: make suggestions on marketing plan based on customer segmentations.

## II. Prepare
### 1. Information about Data Source

Provided by Dr. Omar Romero-Hernandez

### 2. Limitation of Dataset
Data 

### 3. Information about columns

*People*

ID: Customer's unique identifier  
Year_Birth: Customer's birth year  
Education: Customer's education level  
Marital_Status: Customer's marital status  
Income: Customer's yearly household income  
Kidhome: Number of children in customer's household  
Teenhome: Number of teenagers in customer's household  
Dt_Customer: Date of customer's enrollment with the company  
Recency: Number of days since customer's last purchase  
Complain: 1 if the customer complained in the last 2 years, 0 otherwise

*Products*

MntWines: Amount spent on wine in last 2 years  
MntFruits: Amount spent on fruits in last 2 years  
MntMeatProducts: Amount spent on meat in last 2 years  
MntFishProducts: Amount spent on fish in last 2 years  
MntSweetProducts: Amount spent on sweets in last 2 years  
MntGoldProds: Amount spent on gold in last 2 years  

*Promotion*

NumDealsPurchases: Number of purchases made with a discount  
AcceptedCmp1: 1 if customer accepted the offer in the 1st campaign, 0 otherwise  
AcceptedCmp2: 1 if customer accepted the offer in the 2nd campaign, 0 otherwise  
AcceptedCmp3: 1 if customer accepted the offer in the 3rd campaign, 0 otherwise  
AcceptedCmp4: 1 if customer accepted the offer in the 4th campaign, 0 otherwise  
AcceptedCmp5: 1 if customer accepted the offer in the 5th campaign, 0 otherwise  
Response: 1 if customer accepted the offer in the last campaign, 0 otherwise  

*Place*

NumWebPurchases: Number of purchases made through the company’s website  
NumCatalogPurchases: Number of purchases made using a catalogue  
NumStorePurchases: Number of purchases made directly in stores  
NumWebVisitsMonth: Number of visits to company’s website in the last month  

## III. Process
### 1. Import Data to Excel
2240 rows imported.

### 2. Detect abnomalities (outliers, null, empty values...)
#### Outliers

- Year_birth: Data was collected from 2012-2014, customers whose year_birth before 1903 must be an error. Drop 3 rows.
- Income: income values > 113734 are outliers. Drop 8 rows.
- Products and place columns: there are too many outliers, keep them for further analysis

#### Null and empty cells
- Income: 24 nulls. Assume that income depend on age and education level, I calculate average income of each age-education combination and assign that value to corresponding null.

#### Actions
- Delete rows where year_birth and income values are outliers. 11 rows total.
- Assign values to null cells in Income columns

## IV. Analyze
### 1. Assumptions: 
Find relationships between customers's age, education, family and their behaviours:
- Combine all product values to calculate total spend column.
- Assign new values to category features: education, marital_status and income.
- Combine kidhome, teenhome and marital_status to calculate family size.
- Combine NumWebPurchases, NumCatalogPurchases, NumStorePurchases columns to calculate total purchase column.
- Create Pivot Tables to find relationships.

### 2. Findings
Customers dataset is divided into 5 clusters:
- High income - high spend  (1)
- High income - low spend (2)
- Average income - high spend (3)
- Average income - low spend (4)
- Low income - low spend (5)

## V. Suggestions
- Cluster 1:	They earn a lot and also spend a lot, not care much about discount. Show them the best quality products
- Cluster 2:	They buy just a little less time than cluster 1 (mostly through catalog), but average spend is much smaller. The products might not suit their likings. Diverse the products to find more about them
- Cluster 3:	They buy the most times, they like discount and wines. Show them higher price products with some discount might work
- Cluster 4:	They also like discount, but buy much less times and much less expenses. They quite like the web. Use web to attract them, maybe by discounting
- Cluster 5:	They really like the web, but might not have products suit their budget. Find more lower price products to attract this type of customers

## VI. Future Analysis
- Is cluster demography affect cluster behaviours?
- Suggest better ideals with more indepth findings.

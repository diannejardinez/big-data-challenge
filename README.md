# ETL on Big Data - PySpark & AWS's Relational Databases

## Level 1 Objective:

Perform ETL process completely in the cloud and upload a DataFrame to an RDS instance by creating 4 DataFrames to match production-ready tables from two big Amazon customer review datasets

### ETL: Outdoors Dataset
- Extracted: 2,302,173 number of records
- Transformed
![](https://github.com/diannejardinez/big-data-challenge/blob/master/Images/Outdoors-Table-Query/Outdoors-Schema-all_tables.png)
- Load
![](https://github.com/diannejardinez/big-data-challenge/blob/master/Images/Outdoors-Table-Query/Outdoors-RDS-all_tables.png)



### ETL: Digital Video Games Dataset
- Extracted: 145,431 number of records
- Transformed
![](https://github.com/diannejardinez/big-data-challenge/blob/master/Images/Digital_Video_Games-Table-Query/Video_games-Schema-all_tables.png)
- Load
![](https://github.com/diannejardinez/big-data-challenge/blob/master/Images/Digital_Video_Games-Table-Query/Video_games-RDS-all_tables.png)




## Level 2 Objective: 
Analyze whether reviews from Amazon's Vine program are trustworthy. In-depth Analysis was made on Outdoors dataset due to Digital Video Games not having any Vine customers documented



| Analysis Topic    | Vine Customer | Non-Vine Customer  |
| -------------     | ------------- | -------------      |
| Number            | 3137          | 2299036            | 
| Percentage        | 0.14%         | 99.86%             | 
| Ave. star rating  | 4.37          | 4.24               |
| Top Product of VC*| ---           | Same score as VC   |
| Low Product of VC*| Same score as VC/not purchased | Same score as VC   |
| Top Product of NV*| ---           | Same score as VC   |
| Low Product of NV*| Not rated/purchased | Not rated/purchased |
# ETL on Big Data - PySpark & AWS's Relational Databases

## Level 1

**Objective**: Perform ETL process completely in the cloud and upload a DataFrame to an RDS instance by creating 4 DataFrames to match production-ready tables from two big Amazon customer review datasets

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




## Level 2 

**Objective**: Analyze whether reviews from Amazon's Vine program are trustworthy.

### Outdoors Dataset

**Overall Analysis**: Amazon's Vine program reviews should be met with caution. Though customers in this program may be small, their reviews are mirrored by Non-Vine customers(when looking at extreme rating scores of 5 and 1.) In-depth Analysis on Outdoors dataset was performed due to Digital Video Games not having any Vine customers documented. 


**Summary Analysis**: 
|                       | Vine Customer                  | Non-Vine Customer  |
| -------------         | -------------                  | -------------      |
| Number                | 3137                           | 2299036            | 
| Percentage            | 0.14%                          | 99.86%             | 
| Average star rating   | 4.37                           | 4.24               |
| Top Product of VC*    | ---                            | Same score as VC   |
| Low Product of VC*    | ---                            | Same score as VC   |
| Top Product of NV*    | Not purchased                  | ---                |
| Low Product of NV*    | Not rated/purchased            | ---                |
| Reviews created*      | 1-2                            | \~200+             |

*VC: Vine Customer*, 
*NV: Non-Vine Customer*.
*Customer reviews from the top three helpful voting scores* 




**Additional**: 
- Vine customers with the top helpful votes provided 1-2 reviews with their first as the highest, and second as lowest. Non-Vine customers made more reviews. These results match the intention of the Vine program where there is a limited number of members and their rank/ability to stay as a Vine member is by their helpful votes score

- Products from top and low star ratings from Non-Vine customers were not found in product reviews from Vine customers

- Data on star ratings and Vine/Non-Vine customers only looked into three products with the highest helpful votes for each type of customer, this was executed due to helpful votes being a quantifiable metric where customers can gauged as to whether a review seems to be an accurate description of the product and the product experience

- Future research would be to examine "Amazon's Choice" and "Best Seller" products and whether this statement influences ratings or product purchase



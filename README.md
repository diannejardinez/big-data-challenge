# ETL on Big Data - PySpark & AWS's Relational Databases - Analysis

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

**Overall Analysis**: Amazon's Vine program reviews should be met with caution. Though customers in this program may be small, their reviews are mirrored by Non-Vine customers(when looking at extreme rating scores of 5 and 1.) In-depth Analysis only on Outdoors dataset was performed due to Digital Video Games not having any Vine customers documented. 


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

*\*VC: Vine Customer*, 
*NV: Non-Vine Customer*.
*Customer reviews from the top three helpful voting scores from 1 and 5 star ratings* 




**Additional**: 
- Vine customers with the top helpful votes provided 1-2 reviews with their first as the highest, and second as lowest. Non-Vine customers made more reviews. These results match the intention of the Vine program where there is a limited number of members and their rank/ability to stay as a Vine member is by their helpful votes score

- Products from top and low star ratings from Non-Vine customers were not found in product reviews from Vine customers

- Data for star ratings and Vine/Non-Vine customers only looked into three products with the highest helpful votes for each type of customer. This was executed due to helpful votes being a quantifiable metric where customers can gauged as to whether a review seems to be an accurate description of the product and the product experience

- Future research would be to examine "Amazon's Choice" and "Best Seller" products and whether this statement actually influences ratings or product purchase



---

# ETL on Big Data - PySpark & AWS's Relational Databases - Instructions

## Background

In this assignment you will put your ETL skills to the test. Many of Amazon's shoppers depend on product reviews to make a purchase. Amazon makes these datasets publicly available. However, they are quite large and can exceed the capacity of local machines to handle. One dataset alone contains over 1.5 million rows; with over 40 datasets, this can be quite taxing on the average local computer. Your first goal for this assignment will be to perform the ETL process completely in the cloud and upload a DataFrame to an RDS instance. The second goal will be to use PySpark or SQL to perform a statistical analysis of selected data.

There are two levels to this homework assignment. The second level is optional but highly recommended.

1. Create DataFrames to match production-ready tables from two big Amazon customer review datasets.
2. Analyze whether reviews from Amazon's Vine program are trustworthy.

- - -

## Instructions

### Level 1

* Use the furnished schema to create tables in your RDS database.

* Create two separate Google Colab notebooks and **extract** any two datasets from the list at [review dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt), one into each notebook.

  **Note:** It is possible to ETL both data sources in a single notebook, but due to the large data sizes, it will be easier to work with these S3 data sources in two separate Google Colab notebooks.

* Be sure to handle the header correctly. If you read the file without the header parameter, you may find that the column headers are included in the table rows.

* For each notebook (one dataset per notebook), complete the following:

  * Count the number of records (rows) in the dataset.

  * **Transform** the dataset to fit the tables in the [schema file](../Resources/schema.sql). Be sure the DataFrames match in data type and in column name.

  * **Load** the DataFrames that correspond to tables into an RDS instance. **Note:** This process can take up to 10 minutes for each. Be sure that everything is correct before uploading.

### Level 2 (Optional)

In Amazon's Vine program, reviewers receive free products in exchange for reviews.



Amazon has several policies to reduce the bias of its Vine reviews: [https://www.amazon.com/gp/vine/help?ie=UTF8](https://www.amazon.com/gp/vine/help?ie=UTF8).

But are Vine reviews truly trustworthy? Your task is to investigate whether Vine reviews are free of bias. Use either PySpark or—for an extra challenge—SQL to analyze the data.

* While there are no hard requirements for the analysis, consider steps you can take to reduce noisy data, e.g., filtering for reviews that meet a certain number of helpful votes, total votes, or both.



## Resources

[customer review datasets](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt)

- - -



### Copyright

Trilogy Education Services © 2019. All Rights Reserved.



# Amazon Vine Analysis


## Objective

Like the majority of shoppers, Amazon's shoppers depend on product reviews to make a purchase decisions. Amazon makes their vine review datasets publicly available https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt. Vine reviews are quite large and can exceed the capacity of local machines to handle; hence, we are using Spark and AWS.

The first goal for this assignment will be to perform the ETL process completely in the cloud and upload a DataFrame to an RDS instance. The second goal will be to use PySpark to perform a statistical analysis of selected data.

## Resources

Technologies Used:
- AWS RDS S3
- Google Colab Notebooks
- Python
- PySpark


### Amazon Dataset

Toys:  https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Toys_v1_00.tsv.gz

DATA COLUMNS:
marketplace - 2 letter country code of the marketplace where the review was written.
customer_id - Random identifier that can be used to aggregate reviews written by a single author.
review_id - The unique ID of the review.
product_id - The unique Product ID the review pertains to. In the multilingual dataset the reviews
for the same product in different countries can be grouped by the same product_id.
product_parent - Random identifier that can be used to aggregate reviews for the same product.
product_title - Title of the product.
product_category - Broad product category that can be used to group reviews
(also used to group the dataset into coherent parts).
star_rating - The 1-5 star rating of the review.
helpful_votes - Number of helpful votes.
total_votes - Number of total votes the review received.
vine - Review was written as part of the Vine program.
verified_purchase - The review is on a verified purchase.
review_headline - The title of the review.
review_body - The review text.
review_date - The date the review was written.

## Results

### Statistical Analysis to find bias
We notice that the number of non member votes is much larger than the member votes. <br>
![# Reviews by member type](./Resources/VineversusNonVine.png)

This leads us to the conclusion that there is a non factor of positive bias being a member of the Vine program.
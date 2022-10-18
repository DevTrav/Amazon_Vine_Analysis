# Amazon Vine Analysis

## Overview
This project is to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

## Approach
- Out of approximately 50 datasets, I chose to analyze video game reviews. 
- Use PySpark to perform the ETL process to extract the dataset from an S3 bucket, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. 
- Use PySpark to determine if there is any bias toward favorable reviews from Vine members in the dataset. 

## Software and tools for analysis

- [Google Colab](https://colab.research.google.com)
- [pgAdmin](https://www.pgadmin.org)
- [PySpark](https://spark.apache.org/docs/latest/api/python/getting_started/install.html)
- [Java 8](https://www.oracle.com/java/technologies/downloads/)
- [AWS RDS](https://aws.amazon.com/rds/)
- [ VS Code](https://code.visualstudio.com/download)

## Analysis

### Filtering the dataset for total_votes greater than or equal to 20

- The data was filtered to reviewers with more than 20 total votes, on verified purchases. This provides a more consistant Vine program trends.
- The filtered total is `65379` reviews

```
vote_count = df.filter("total_votes >= 20")
vote_count.show()
vote_count.count()
```


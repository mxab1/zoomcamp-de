# Module 3
## Question 1
    SELECT count(*) FROM `zoomcamp-de-448313.module3.yellow_tripdata_external`
-> 20332093

## Question 2
    SELECT COUNT(DISTINCT PULocationID) as NUM_PU_L FROM `zoomcamp-de-448313.module3.yellow_tripdata_external`
    SELECT COUNT(DISTINCT PULocationID) as NUM_PU_L FROM `zoomcamp-de-448313.module3.yellow_tripdata_native`

-> 0MB and 155.12MB

## Question 3
    SELECT PULocationID FROM `module3.yellow_tripdata_native` -> 155 MB
    SELECT PULocationID, DOLocationID FROM `module3.yellow_tripdata_native` -> 310 MB


## Question 4
    SELECT COUNT(*) as ZERO_FARES FROM `zoomcamp-de-448313.module3.yellow_tripdata_native` WHERE fare_amount = 0
-> 8333

## Question 5
Partition by tpep_dropoff_datetime and Cluster on VendorID

    CREATE OR REPLACE TABLE `zoomcamp-de-448313.module3.yellow_tripdata_partitoned_clustered`
    PARTITION BY DATE(tpep_dropoff_datetime)
    CLUSTER BY VendorID AS
    SELECT * FROM `zoomcamp-de-448313.module3.yellow_tripdata_external`;

## Question 6

    SELECT COUNT(DISTINCT PULocationID) FROM `zoomcamp-de-448313.module3.yellow_tripdata_native`
    WHERE DATE(tpep_dropoff_datetime) BETWEEN '2024-03-01' AND '2024-03-15';

    SELECT COUNT(DISTINCT PULocationID) FROM `zoomcamp-de-448313.module3.yellow_tripdata_partitoned_clustered`
    WHERE DATE(tpep_dropoff_datetime) BETWEEN '2024-03-01' AND '2024-03-15';

-> 310.24MB and 26.84MB

## Question 7
GCP Bucket

## Question 8
false, depends

## Question 9

# columns to drop

* #### amount\_tsh because 75% is 0 and contain values like 350000



* #### wpt\_name - Name of the waterpoint if there is one



* #### num\_private - we dont know the meaning of this column



* #### subvillage - 19000 unique values



* #### region - cause we have region\_code column



* #### lga (Local Government Area): This is just the text name for the district\_code (e.g., District 1 might be "Bagamoyo"). It provides duplicate information.



* #### ward: This is a sub-unit of the district. It has 2,000+ unique values.



* #### recorded\_by - Group entering this row of data



* #### extraction\_type - The kind of extraction the waterpoint uses



* #### extraction\_type\_class - The kind of extraction the waterpoint uses



* #### management\_group - already have more detailed management column 



* #### payment\_type - already have payment column redundant



* #### quality\_group - already have water quality more detailed



* #### quantity\_group - already have quantity both are same



* #### source\_type and source\_class - already have more detailed source column



* #### waterpoint\_type\_group - already have more detailed water\_type feature







# columns to preprocess with details



1. fill zeros in construction year with regional\_code and district\_code wise median create new column age\_pump when last visited
   
   ---
2. for funders keep to 15 funders name rest as others and rename funder 0 as unknown
   
   ---
3. for gps\_height replace 0 and negative values with median by regional\_code and district\_code
   
   ---
4. convert installers name in lower case keep top 15 installers and rest in others
   
   ---
5. many latitude longitude has 0 values hande them by replace zeros with median distric\_code and regional\_code wise
   
   ---
6. create new column missing\_population 1 if population is 0 other wise 0 and replace all 0 in population by taking median regional\_code and district\_code wise
   
   ---
7. public\_meeting - convert it into 0 or 1 and fill missing values by taking median regional\_code and district\_code
   
   ---
8. #### scheme\_management- fill null values by taking mode region\_code and district\_code wise



#### 9\. permit - replace null values with 3(unknown)



#### 10\. construction\_year - Add a column construction\_year\_missing (1 if it was 0, else 0). This tells the model "We guessed this date." and Replace 0 with the district region median.








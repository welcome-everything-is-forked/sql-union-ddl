# sql-union-ddl
## Standard criteria
### Data manipulation language
Go over to this [Kaggle](https://www.kaggle.com/datasets/anikannal/solar-power-generation-data?select=Plant_1_Weather_Sensor_Data.csv) page, read carefully the description of the dataset as well as the description of each column in the data. There are two sets of data collected for 2 power plants: the “Generation Data” and the ”Weather Sensor Data”:
1. Download the four csv files using the Download button at the top of the page (it will download them into a zipped folder, so make sure you unzip the folder);
2. Move over to BigQuery, below your personal project create a new data set and name it “SolarPower”;
3. In the newly created data set, upload the four files into four separate tables (give to each table the corresponding file name); in the end you should have a situation similar to the one the screenshot below:
![alt text](image.png)
4. Open a new editor window and write a query that combines the two pairs of datasets to have Plant 1 and Plant 2 in the same table and a total of two resulting tables. CREATE those two TABLEs AS the result of the UNION between the above mentioned tables and call them “Generation_Data” and “Weather_Sensor_Data”; your SolarPower data set should now look like this:
![alt text](image-1.png)
5. How many inverters (hint: source_key) are there in each plant?
6. How many days of observations do we have for each plant?
7. Which inverter generated the highest total yield? Which plant does it belong to? Hint: careful with the aggregation function you use with the total_yield field, read carefully its description on the kaggle page.
### Data definition language
Using the sqliteonline environment, create the following two tables (from the previous lesson on Joins) specifying the correct schemas (column names, data types, etc)
1. Create the “students” table:
students
![alt text](students.png)
2. Create the “courses” table:
courses
![alt text](courses.png)
3. Use all four types of JOINs as we saw them in lesson 2.7.17 and familiarise yourself with how JOINs work and when null values are generated and think about what that happens.
4. There is an error in the students table, change Sara’s idCourse from 6 to 4.
5. There is an error also in the courses table, change the name of idCourse = 5 from “History” to “Economics”.
6. There is a new student in the class, his name is “George” and he is going to follow the Economics course; add a new row of data to the students table containing the new student’s  information.
7. How have these changes affected the relationship between the two tables?
   a. Think about it and try to visualise in your head how the results from the four types of JOINs will change now.
   b. Then replicate the work you did at point 3. with the new tables.
## Advanced Exercise (optional):
Using the “bigquery-public-data.thelook_ecommerce” data set, perform the following tasks:
1. JOIN the order_item table with the products table and return the joined table
2. Write a query that shows each product categories sorted by number of orders per category
3. Using the last query as the base, add the average margin per order for each category. Notice how top selling categories may not have the highest relative margins. (Hint: margin = retail_price - cost)
4. Which product(s) is/are the most popular (number sold)?
5. Which product takes the longest time (in terms of number of minutes) from shipping to delivery?
6. Which product takes the shortest time?
7. Did you notice something strange in the last result? You should have seen some null values among the “avg_hr_ship_deliver” variable, why do you think that is? Write a query that checks if there are any null values in “delivered_at”. What do you think a null value means in such a column?
8. Back to the query at point 6, add a WHERE condition that excludes items that have not been delivered yet:
9. When you answered question five, all those items that took the longest time from shipping to delivery were only ordered one or two times; answer to the same question but only for those products that were sold at least 5 times.

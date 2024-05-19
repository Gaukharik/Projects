## Profile & prepare the data 

My first objective is to ingest the data from raw CSV files, conduct some data profiling, feature engineering and QA, and build a custom calendar to track performance by day, week, month, quarter and year.

1. Connect to the Sales CSV file and profile the data. How many orders were recorded? Over what time period? Is there anything interesting about delivery dates? Add a TransactionKey field to uniquely identify each row.

I loaded Sales CSV through Power Query:

![](/Global_Electronics_Retailer/screenshots/connecting_to_sales.png)

Then I checked columns quality:

![](/Global_Electronics_Retailer/screenshots/data_profiling.png)

Everything seem correct, except Delivery Date column, which has 86% empty values. 

If we uncheck the null values in Delivery Date column, then we can see that only 0 values appear in StoreKey column. We don't know what does it mean yet, as we haven't loaded store csv file yet. But we need to keep in mind this fact. To summurize the only store that has valued delivery dates is store 0. 

![](/Global_Electronics_Retailer/screenshots/zero_values_on_storekey.png)

To answer the question "How many were recorded?" I will use column profile option.
By navigating to Order Number column, we can see that there were 26326 orders.

![](/Global_Electronics_Retailer/screenshots/how_many_orders_were_recorded.png)

The orders were made between 2016-01-01 and 2021-02-20. 

![](/Global_Electronics_Retailer/screenshots/order_dates.png)

And now let's add TransactionKey field (the primary key)

![](/Global_Electronics_Retailer/screenshots/adding_transactionkey_primary_key.png)

2. Connect to the Products CSV file and profile the data. What does the company sell? How many distinct categories and subcategories do you see?

What does the company sell? 

![](/Global_Electronics_Retailer/screenshots/distinct_categories_company_sells.png)

Seems like the company sells 8 distinct product categories, such as home appliances, computers, cameras and camcoders, cell phones, TV and Video, games and toys, audio, music, movies and audio books. The most popular category is home appliances.

And there 32 distinct product subcategories:

![](/Global_Electronics_Retailer/screenshots/distinct_subcategories.png)

The most popular subcategory is computer accessories, followed by lamps. 

There are no empty values in the entire table.


3. Connect to the Stores CSV file and profile the data. How many stores does company operate? Do you notice any that aren’t like the others?

Firtst let's load the csv to power query editor:

![](/Global_Electronics_Retailer/screenshots/loading_stores_table.png)

And answer question "How many stores does company operate?":

![](/Global_Electronics_Retailer/screenshots/distinct_stores.png)

So company operates 67 stores.

If we look close to Squere meters column 1% is empty values. When filtering, we can see that it is online store:

![](/Global_Electronics_Retailer/screenshots/null_value_square_m.png)

When we analyzed Sales table we noticed that the only store that has valued delivery dates is store 0. Which means that were online orders. 

4. Connect to the Exchange_Rates CSV file and profile the data. What information does this table contain, and how could it be used?

Let's load Exchange_Rates CSV.

![](/Global_Electronics_Retailer/screenshots/loading_exchange_rates.png)

So what we can see from this table is that all the prices in Sales table are in USD dollars. This table helps to convert the currency, based on where the transaction takes place. 

5. Connect to the Customers CSV file and profile the data. How many customers has the company served? Where are customers primarily located?

![](/Global_Electronics_Retailer/screenshots/loading_customers_table.png)

How many customers has the company served?

![](/Global_Electronics_Retailer/screenshots/number_of_customers.png)

It seems that the company serves 15266 customers.

Where are customers primarily located?

![](/Global_Electronics_Retailer/screenshots/customers_location.png)

As we can see 44% of the customers located in USA. And only 4% in Italy. 

Based on Birthday column I added Age column, to see customers' age.

![](/Global_Electronics_Retailer/screenshots/adding_age_column.png)

Then we need to add conditional column in order to put customers in different age buckets:

![](/Global_Electronics_Retailer/screenshots/adding_conditional_column.png)

So now we have new column Age Range based on customers' age column:

![](/Global_Electronics_Retailer/screenshots/age_range.png)

6. Create a Calendar table that contains a list of contiguous dates (no gaps) and reflects the same date range as the Sales table, then add new columns for Day Name, Start of Week/Month/Quarter, and Year.

We duplicated Sales table and removed all the columns except Order Date column. Then renamed it to Date column and removed duplicates from it:

![](/Global_Electronics_Retailer/screenshots/calendar_table.png)

Then I added Day (name of the day), start of week, start of month, start of quarter and year columns, which will be helpful to gain some analysis in future tasks.

![](/Global_Electronics_Retailer/screenshots/adding_additional_date_formats.png)

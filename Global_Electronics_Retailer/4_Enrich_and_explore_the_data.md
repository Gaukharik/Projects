## Enrich & Explore the Data

My third objective is to enrich the data model by adding calculated measures to track key business metrics, including total orders, revenue, average order value and delivery time.

1. Add a blank, dedicated measures table

In our power pivot we added blank table for measures:

![](/Global_Electronics_Retailer/screenshots/adding_blank_table.png)

2. Create a new measure to calculate Total Orders, based on Order Number. How has order volume trended over time? Do all product categories show a similar trend?

Then we created new measure to calculate Total Orders, based on Order Number:

![](/Global_Electronics_Retailer/screenshots/adding_measure_for_order_numbers.png)

We inserted pivot table from Data Model:

![](/Global_Electronics_Retailer/screenshots/creating_pivot_table.png)

How has order volume trended over time?

![](/Global_Electronics_Retailer/screenshots/order_trends.png)

Do all product categories show a similar trend?

If we go deeper and add months and visualize it with line chart we can see that till the beginning of 2020 the trend was the same and after that period it dropped and never increased:

![](/Global_Electronics_Retailer/screenshots/visualizing_trends.png)

And seems that the trend is the same for all product categories. 

3. Calculate Total Revenue (USD), based on Quantity and Unit Price (USD). Which stores generate the most revenue? Which individual products? Create another version to calculate revenue in local currency.

In order to calculate Total Revenue (USD), based on Quantity and Unit Price (USD) we created new measure:

![](/Global_Electronics_Retailer/screenshots/adding_total_revenue_measure.png)

Which stores generate the most revenue?

![](/Global_Electronics_Retailer/screenshots/store_revenue.png)

From this pivot table we can see that Store 0 generated the most revenue, which is online store. 

Create another version to calculate revenue in local currency.

To convert USD to local currencies depending where the transactions took place, we needed to create Total Revenue for local currency. To do that we created new measure:

![](/Global_Electronics_Retailer/screenshots/adding_total_revenue_measure_local.png)

4. Calculate Average Order Value (AOV), based on Total Revenue (USD) and Total Orders. How does AOV compare across product categories? Are there differences based on customer age?

To calculate Average Order Value (AOV), based on Total Revenue (USD) and Total Orders we created new measure:

![](/Global_Electronics_Retailer/screenshots/AOV.png)

How does AOV compare across product categories?

![](/Global_Electronics_Retailer/screenshots/aov_and_categories.png)

So we can see that home appliances has the highest AOV. 

Are there differences based on customer age?

![](/Global_Electronics_Retailer/screenshots/age_and_aov.png)

There are no significant differences based on customer ages. 

5. Calculate Average Delivery Time, in days. Which types of products tend to be delivered fastest or slowest?

Let's calculate Average Delivery Time, in days. To do that we add new measure:

![](/Global_Electronics_Retailer/screenshots/average_delivery_date.png)

Which types of products tend to be delivered fastest or slowest?

![](/Global_Electronics_Retailer/screenshots/category_delivery.png)

From this table we can see that on average all product categories delivery time is pretty the same around 4-5 days.  
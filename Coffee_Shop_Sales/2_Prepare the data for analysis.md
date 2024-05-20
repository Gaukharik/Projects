## Prepare the data for analysis

My first objective is  to explore the coffee shop dataset, conduct some basic data QA and profiling, and add calculated date and time fields to prepare the data for analysis.

1. How many transactions were recorded, over what period of time? What products and product categories were sold?

![](/Coffee_Shop_Sales/screenshots/table_overview.png)

So we have 149,116 transactions total. 

As I'm first exploring this data, what is our transaction date range here?

![](/Coffee_Shop_Sales/screenshots/transactions_date_range.png)

So as we can see we have range from January 2023 till June 2023.

We also have transactions time, seem to start around 6:00 AM

![](/Coffee_Shop_Sales/screenshots/timestamp.png)

We have 3 store locations: Astoria, Hell's Kitchen and Lower Manhattan. 

![](/Coffee_Shop_Sales/screenshots/store_locations.png)

We can drill into our unit prices and start to get a sense of the range. 

![](/Coffee_Shop_Sales/screenshots/price_range.png)

It looks like the cheapest product is Regular Syrup and the expensive one is Premium Beans.

We can drill into start to understand some of the product information as well. So it looks like company sells bakery items, branded items, which might be apparel or merchandise coffee, coffee beans, drinking chocolate flavours, loose tea, packaged chocolate and tea. So pretty standard fare for a coffee shop. 

![](/Coffee_Shop_Sales/screenshots/product_category.png)

This is all making sense. I don't see any obvious QA issues like missing data, outliers, miscategorized text. 

2. Add a new column to calculate Revenue (price * quantity)

The revenue is transaction_qty times init_price.

![](/Coffee_Shop_Sales/screenshots/adding_revenue_column.png)

3. Add new columns to calculate Month and Day of Week based on the transaction date (ALSO: display them as text (ie “Jan”, “Feb”, “Sun”, “Mon”), instead of numerical values)

Let's add month column:

![](/Coffee_Shop_Sales/screenshots/calculating_month.png)

To calculate weekday we use Weekday function:

![](/Coffee_Shop_Sales/screenshots/calculating_weekday.png)

Now let's define month name:

![](/Coffee_Shop_Sales/screenshots/calculating_month_name.png)

![](/Coffee_Shop_Sales/screenshots/calculating_month_name1.png)

To define weekday name we use Text function as well:

![](/Coffee_Shop_Sales/screenshots/calculating_weekday_name.png)

![](/Coffee_Shop_Sales/screenshots/calculating_weekday_name1.png)

4. Add a new column to extract Hour from the transaction time

![](/Coffee_Shop_Sales/screenshots/calculating_hour.png)

![](/Coffee_Shop_Sales/screenshots/calculating_hour1.png)

So this is how our table looks after adding additional columns:

![](/Coffee_Shop_Sales/screenshots/final_table_look.png)
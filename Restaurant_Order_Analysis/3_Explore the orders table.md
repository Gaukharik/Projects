## Explore the order_details table to get the idea of the data that's been collected

My second objective is to better understand the orders table by finding the date range, the number of items within each order, and the orders with the highest number of items.

1. View the order_details table

![](/Restaurant_Order_Analysis/screenshots/order_table.png)

So we have order_details_id, order_id, order_date, order_item and item_id columns in this table. 

The order_details_id is the primary key for our table. 

2. What is the date range of the table?

![](/Restaurant_Order_Analysis/screenshots/date_range.png)

So we can see that the date range was from 1st January 2023 till 31st of March 2023. 

3. How many orders were made within this date range? 

![](/Restaurant_Order_Analysis/screenshots/order_numbers.png)

I can see that within that date range 5370 orders were made. 

4. How many items were ordered within this date range?

![](/Restaurant_Order_Analysis/screenshots/items_number.png)

So it seems like 12234 items were ordered within this date range.

5. Which orders had the most number of items?

![](/Restaurant_Order_Analysis/screenshots/most_number_items.png)

So in each order there were 14 dishes that were ordered. 

6. How many orders had more than 12 items?

![](/Restaurant_Order_Analysis/screenshots/more_than_12.png)

So there were 20 orders that had more than 12 items. 

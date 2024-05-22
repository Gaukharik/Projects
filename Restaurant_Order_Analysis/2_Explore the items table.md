## Explore the items table to get an idea of what's on the new menu

My first objective is to better understand the items table by finding the number of rows in the table, the least and most expensive items, and the item prices within each category.

Let's have a look to our database:

![](/Restaurant_Order_Analysis/screenshots/db_overview.png)

As we can see there are two tables in this database: menu_items and order_items.

1. View the menu_items table

![](/Restaurant_Order_Analysis/screenshots/menu_items.png)

So menu_items table contains menu_item_id, item_name, category and price columns. The category seems to be American, Asian, Mexican and Italian. 

Next let's find the numbers on this menu.

2. Find the number of items on the menu

![](/Restaurant_Order_Analysis/screenshots/itens_count.png)

As we can see there are 32 rows in this table. Let's move to the next question. 

3. What are the least and most expensive items on the menu?

To find the least and most expensive items I'm going to sort the table by price column using ORDER BY:

![](/Restaurant_Order_Analysis/screenshots/least_exp_item.png)

So it looks like my least expensive item is Edamame which is Asian food and the price is 5$.

![](/Restaurant_Order_Analysis/screenshots/most_exp_item.png)

And my most expensive item is Shrimp Scampi, which is Italian food and the price is 19.95$.

4. How many Italian dishes are on the menu? 

![](/Restaurant_Order_Analysis/screenshots/italian_dishes.png)

So there are 9 Italian dishes on the menu.

5.What are the least and most expensive Italian dishes on the menu?

![](/Restaurant_Order_Analysis/screenshots/least_Exp_italian.png)

So the least expensive Italian dish is Spaghetti which is 14.5$.

![](/Restaurant_Order_Analysis/screenshots/most_exp_italian.png)

The mosth expensive Italian dish is Shrimp Scampi which is 19.95$.

6. How many dishes are in each category? 

Now I want to know how many dishes are in each category.

![](/Restaurant_Order_Analysis/screenshots/count_category.png)

7.What is the average dish price within each category?

![](/Restaurant_Order_Analysis/screenshots/avg_price.png)

And from this output we can see that Italian dishes are the most expensive versus American dishes which is more affordable. 
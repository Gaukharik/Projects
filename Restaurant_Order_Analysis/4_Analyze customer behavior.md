## Use both tables to understand how customers are reacting to the new menu

My final objective is to combine the items and orders tables, find the least and most ordered categories, and dive into the details of the highest spend orders.

1. Combine the menu_items and order_details tables into a single table

So let's look at two tables again:

![](/Restaurant_Order_Analysis/screenshots/obj3_task1.png)

![](/Restaurant_Order_Analysis/screenshots/orders.png)

Now our goal is to combine these two tables. So from menu_items table we have menu_item_id field. And then from order_details, we have item_id field and those two represent the same concept, which is specific item on the menu.

So to combine these two tables, we're going to have to join these two tables on this item_id.

![](/Restaurant_Order_Analysis/screenshots/joined.png) 

Our two tables have been joined. So we can see all order details infromation on the left, and item_id has matched with menu_item_id. 

2. What were the least and most ordered items? What categories were they in?

Let's first see how many times each item was ordered:

![](/Restaurant_Order_Analysis/screenshots/item_purchased.png) 

And I want to find top 5 I need to sort this table:

![](/Restaurant_Order_Analysis/screenshots/least_ordered_item.png) 

We can see that least ordered item was Chicken Tacos. 

![](/Restaurant_Order_Analysis/screenshots/most_ordered_item.png)

And the most ordered item was Hamburger.

Our next question is to define what categories were these items were in.
To do that I will add category field to my query:

![](/Restaurant_Order_Analysis/screenshots/category1.png)

So the Hamburger is in American food category.

![](/Restaurant_Order_Analysis/screenshots/category2.png)

And Chicken Tacos is in Mexican food category.

3. What were the top 5 orders that spent the most money?

![](/Restaurant_Order_Analysis/screenshots/top5.png)

So here we can see top 5 orders that spent the most money. 

Now let's dive in to those specific orders.

4. View the details of the highest spend order. Which specific items were purchased?

Our highest spend order is 440. 

Let's look at what order_id 440 ordered.

![](/Restaurant_Order_Analysis/screenshots/440id.png)

I want to know how much of each category that they ordered:

![](/Restaurant_Order_Analysis/screenshots/count440.png) 

The order_id 440 ordered a lot Italian items, and not so many the rest. 

That's interesting, because even though Italian items weren't the most popular thing on the menu, it seems like this highest spend order tends to really like Italian food. So maybe that's something we should keep in our menu. 


5. View the details of the top 5 highest spend orders

Our highest spent order ids: 440,2075,1957,330,2675.

![](/Restaurant_Order_Analysis/screenshots/highest_orderid.png)

We can see that these top five spent orders are ordering more Italian food than all the other types of food. 

Let's separate this out for each specific order. 

![](/Restaurant_Order_Analysis/screenshots/order_categ.png)

I can see what categories they've ordered. 

Just from this top 5 orders we've seen that these highest spend orders, they tend to be spending a lot on Italian food. 

So the insight that we've gathered here is that we should keep these expensive Italian dishes on our menu, because people seem to be ordering them a lot, especially our highest spend customers. 

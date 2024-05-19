## Build a relational data model

My second objective is to build a data model by connecting the foreign keys in the Sales table to the primary keys in each dimension table via 1:many relationships.

1. Create relationships from the Sales table to Customers, Stores, Products and Calendar

Through Power Pivot tab, we open our model:

![](/Global_Electronics_Retailer/screenshots/power_pivot_opening_model.png)

Let's create relationships from the Sales table to Customers, Stores, Products and Calendar

![](/Global_Electronics_Retailer/screenshots/creating_1_to_many_relationships.png)

2. What happens when you try to connect Sales to Exchange Rates? Add a new column to both tables named ExchangeKey and use that field to relate them via a 1:many relationship.

In order to create one-to-many relationships between Exchange Rate and Sales table we need to modify Exchange Rate table. 

We need uniqye key that contains both Currency and Date columns. 

So by merging those two columns we added ExchangeKey primary key, where all values are unique.

![](/Global_Electronics_Retailer/screenshots/exchangekey_creation.png)

Now we need to modify Sales table also.

We added merged column with Order Date and Currency Code and created ExchangeKey foreign key for Sales table. 

![](/Global_Electronics_Retailer/screenshots/foreignkey_for_sales.png)

And now we can create one-to-many relationships between Sales and Exchange Rate tables.

![](/Global_Electronics_Retailer/screenshots/creating_relationships_sales_exchangerates.png)


3. Hide all foreign keys from the Sales table

We need to hide all foreign keys from the Sales table

![](/Global_Electronics_Retailer/screenshots/hiding_keys.png)

4. Split the Products table into category and subcategory-level dimension tables, and update the data model to relate these new tables

We duplicated Products table and kept only SubcategoryKey, Subcategory and CategoryKey columns and named this table Subcategories.

![](/Global_Electronics_Retailer/screenshots/subcategories_table.png)

Then we removed duplicates from SubcategoryKey column. So now we have unique values of Subcategory and CategoryKey columns. 

We need to do the same process for categories too. 

![](/Global_Electronics_Retailer/screenshots/categories_table.png)

Now we can delete Subcategory, Category and CategoryKey columns.

So now our model looks like this:

![](/Global_Electronics_Retailer/screenshots/additional_relationships.png)


## Compare popularity across regions

My third objective is to find the number of babies born in each region, and also return the top 3 girl names and top 3 boy names within each region.

1. Return the number of babies born in each of the six regions (NOTE: The state of MI should be in the Midwest region)

Let's look at the regions table first:

![](/Baby_Name_Trend_Analysis/screenshots/regions.png)

The regions table contains state and region columns.

Let's confirm that there are 6 regions. 

![](/Baby_Name_Trend_Analysis/screenshots/6regions.png)

I see that are actually seven regions. So if I look into this in more detail, then I can see that New England is spelled in two different ways. So first I need to clean this up, and the way I can do that is by using Case statement. 

![](/Baby_Name_Trend_Analysis/screenshots/cleaned_region.png)

We can see all our regions. And if I want to confirm that there are six regions instead of seven regions, I'm gonna make the above query into CTE. 

![](/Baby_Name_Trend_Analysis/screenshots/confirm6regions.png)

Now we can see that if I use clean regions instead of regions, I have six regions. 

But we have another issue the state of MI should be in the Midwest region.

In order to do that we need to join this query with names table, that has all the states. So we can look specifically at the state of Michigan or MI. 

![](/Baby_Name_Trend_Analysis/screenshots/joined_states.png)

And we can see there is a null value. That means that there are some states in the names table that aren't in the clean regions table. So instead of doing DISTINCT, let's look at those exact states. 

![](/Baby_Name_Trend_Analysis/screenshots/cr_regions.png)

And I see that my only result is MI or Michigan. So Michigan is missing a clean region. And I know that Michigan should be in the Midwest region. So let's make that update in our query. 

![](/Baby_Name_Trend_Analysis/screenshots/michigan.png)

I have all my states including Michigan in Midwest region. 

So now I can answer the main question return the number of babies born in each of the six regions.

![](/Baby_Name_Trend_Analysis/screenshots/num_babies_regions.png)

Then we can see for each of the six regions, the number of babies that were born in each region. 

2. Return the 3 most popular girl names and 3 most popular boy names within each region.

Because we're lookimg to popularity I'm going to use ranking with Windows function. But first I need to collect all the columns that I need:

![](/Baby_Name_Trend_Analysis/screenshots/needed_columns.png)

We can see now I have, for each clean region, I had the gender, name and number of babies. So from this I'm going to add a column that's created by a window function. 

![](/Baby_Name_Trend_Analysis/screenshots/pop_region.png)

We have some pretty awesome results here. For each region we have for each gender, the top three baby names. 

So we can see that Jessica is the most popular girl named in the Mid-Atlantic, the same with Midwest, Mountain area, New England, Pacific and South. It looks like everywhere else Jessica was the most popular girl name for those three decades. But in the South Ashley was really popular. 

And as for boy names, Christopher is the most popular in the South. And then Pacific we have Michael. So it seems leke everyone in the US we had Jessica and Michael as the top popular names, but in the South they have different preferences on names. So specifically Ashley and Christopher. 







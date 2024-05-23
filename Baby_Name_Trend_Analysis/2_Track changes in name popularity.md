## Track changes in name popularity

My first objective is to see how the most popular names have changed over time, and also to identify the names that have jumped the most in terms of popularity.

First let's look at our database:

![](/Baby_Name_Trend_Analysis/screenshots/db_overview.png)

So our database contains two table: names and regions.

1. Find the overall most popular girl and boy names and show how they have changed in popularity rankings over the years.

Let's look at the names table:

![](/Baby_Name_Trend_Analysis/screenshots/names.png)

So the names table contains state, gender, year, name and birth columns.
If I need to find most popular girl and boy names I need to aggregate our data. 

![](/Baby_Name_Trend_Analysis/screenshots/pop_girl.png)

It looks like Jessica was the most popular girl name.

Let's do exact same thing but for boy names:

![](/Baby_Name_Trend_Analysis/screenshots/pop_boy.png)

So the most popular boy name was Michael. 

Our next goal is to show how they have changed in popularity rankings over the years.

To do this I can use Windows functions for ranking. Windows functions will help us number the rose by popularity. 

First let's do this for girl names. What I need to do is to create table that has every year, every name, and how many babies were born with that name in that year. 

![](/Baby_Name_Trend_Analysis/screenshots/year.png)

Then we can see for every year the certain names, and how many babies were given that name. 

First look at girl names popularity. 

![](/Baby_Name_Trend_Analysis/screenshots/girl_rank.png)

So here we can see for every year I have the name Jessica. And how its popularity has changed. So in eighties it was 3rd most popular, it got really popular in the nineties, and then it started dropping in popularity in the two thousands. 

Now let's do exact same things but for the boys name. 

![](/Baby_Name_Trend_Analysis/screenshots/boy_rank.png)

So Michael was the most popular name in eighties and then went all the way down to a third ranking in the two thousands. Michael has always been popular boy name.  

2. Find the names with the biggest jumps in popularity from the first year of the data set to the last year

From the previous question we were able to see that our dataset contains data from 1980 all the way to 2009. So let's find the biggest jumps. 

![](/Baby_Name_Trend_Analysis/screenshots/1980.png)

Here we can see our data just for the year of 1980. 

![](/Baby_Name_Trend_Analysis/screenshots/2009.png)

And here is our data just for the year 2009. 

By writing these two CTEs, I'm able to access both of those outputs, the 1980 data and 2009 data. 

So next let's join this data together in order to have 1980 popularities alongside the year 2009 popularities. 

![](/Baby_Name_Trend_Analysis/screenshots/joined.png)

Then we see that we have for every name, I have the 1980 popularity and the 2009 popularity. 

So I want to find the names with the biggest jumps in popularity. So to do that, I'm gonna to substract two popularities to see which one had the biggest increase in popularity. 

![](/Baby_Name_Trend_Analysis/screenshots/substract.png)

Then we can see in my output I have the popularity difference. 

3. What are some fun facts I can share from these findings?

Aidan used to be 5000 something in popularity, but in 2009 it's now almost in the top 100. So Aidan has risen a lot in popularity, so has Skyler, Macy and so on.
So these are some fun facts that we can share in our annual report.  










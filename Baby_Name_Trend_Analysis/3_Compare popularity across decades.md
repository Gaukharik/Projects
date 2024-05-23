## Compare popularity across decades

My second objective is to find the top 3 girl names and top 3 boy names for each year, and also for each decade.

1.For each year, return the 3 most popular girl names and 3 most popular boy names

Our goal is to compare popularity across decades.

First I'm going to find the 3 most popular girl names and 3 most popular boy names. To do that let's start by creating a table that has all the fields that we need:

![](/Baby_Name_Trend_Analysis/screenshots/3_most.png)

Now we can see for every year, genderand name the number of babies that were born. 

With this output table, because we're looking at the three most popular girl names and boy names, we're gonna have to add another column for popularity. So I will turn the above table to CTE:

![](/Baby_Name_Trend_Analysis/screenshots/cte_top3.png)

Then in my output I have for each year and gender only the three most popular names. 

2.For each decade, return the 3 most popular girl names and 3 most popular boy names.

![](/Baby_Name_Trend_Analysis/screenshots/decade.png)

And now we can see the column which used to be Year, but I've combined all those years into a decade using those case statements. I have for each decade, each gender type, what were the top three names. 

And from this I can gather in the eighties, there were a lot of Jessicas, JEnnifers and Amandas. In the nineties, that's when you see Ashley and Emily popup. And then in the two thousands we have Madison and Emma. 

For boy names, we have Michael, Christopher, Matthew, again Michael, Christopher, Matthew in the nineties. And then it actually changes in the two thousands. So we have Jacob, Michael and Joshua. 

So seems like girl names change a lot over the decades. And then for boy names, there's slight changes, but mostly Michael is the most popular boy name. 





## Explore unique names in the dataset

My final objective is to find the most popular androgynous names, the shortest and longest names, and the state with the highest percent of babies named "Chris".

1. Find the 10 most popular androgynous names (names given to both females and males).

To do that we're gonna to look our name table. 

![](/Baby_Name_Trend_Analysis/screenshots/names_table.png)

We have the gender column. So what we can do here is a group by, so that for each name we can see how many genders does that name have. 

![](/Baby_Name_Trend_Analysis/screenshots/distinct_gender.png)

Then we can see that for most names there is one gender associated with it. But, there are some names that have two genders associated with it. So for example Aaron is a name to both boys and girls. We need to filter this table. 

![](/Baby_Name_Trend_Analysis/screenshots/gender2.png)

These are all the names that have two genders associated with them. 

We need to find 10 most popular androgynous names. To do that I need to add a column for a number of babies. 

![](/Baby_Name_Trend_Analysis/screenshots/top10.png)

These are the most common boy names were also given to girls. And then there is some common girl names like Jessica and Ashley that were also given to boys. That is interesting fun fact that we can share in our report. 

2. Find the length of the shortest and longest names, and identify the most popular short names (those with the fewest characters) and long names (those with the most characters).

To find the length of the shortest and longest names we're going to use the Length function. 

![](/Baby_Name_Trend_Analysis/screenshots/length.png)

So here we can see that Jessica has a name, length of seven, Jennifer eight, and so on. 

I want to find the length of the shortest names.

![](/Baby_Name_Trend_Analysis/screenshots/short_name.png) 

It looks like the shortest names are two characters.

Next let's find the length of longest names:

![](/Baby_Name_Trend_Analysis/screenshots/longest.png) 

The longest names are 15 characters. 

Now I need to identify the most popular short names and long names.

![](/Baby_Name_Trend_Analysis/screenshots/short_long.png) 

So we see from this table long and short names. And we need to know the most popular ones.

![](/Baby_Name_Trend_Analysis/screenshots/pop_short.png) 

These output is our most popular short and long names. For short names Ty is really popular. For long names Francisojavier is the most common one. 

3. Find the state with the highest percent of babies named "Chris". 

To calculate the percent we need to create the column for the numerator amd column for the denominator. 

![](/Baby_Name_Trend_Analysis/screenshots/sum_chris.png) 

So this is telling me for each state how many babies were named Chris. And that's gonna give me the numerator of my calculation. I also need denominator of my calculation:

![](/Baby_Name_Trend_Analysis/screenshots/num_babies.png) 

Next I need to join this two tables:

![](/Baby_Name_Trend_Analysis/screenshots/joined_chris.png) 

I have for every state, the number of Chrises and the number of babies. So what I need to do from here is to use this output to divide the numerator by the denominator. 

![](/Baby_Name_Trend_Analysis/screenshots/result.png) 

We can see here that Lousiana has the highest percent of Chrises. So out of all the babies that were born in that state, over 0.03% of them were named Chris. 





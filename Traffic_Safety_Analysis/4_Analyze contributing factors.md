## Analyze contributing factors

My final objective is to find the top 10 contributing factors by number of collisions, and calculate the percentage of the collisions involving injuries or fatalities.

1. Calculate the count of 'Collision ID' by 'Contributing Factor'

To calculate the count of 'Collision ID' by 'Contributing Factor' we will use PivotTable:

![](/Traffic_Safety_Analysis/screenshots/causes.png)

2. Filter the top 10 contributing factors by collisions, and sort them in descending order

Then by applying Top 10 filter on collisions and by filtering descending by collision ID, we've got the following table:

![](/Traffic_Safety_Analysis/screenshots/top10_contributing.png)

So the contributing factor that causes the most collisions is driver inattention or distraction. 

Then interestingly enough, we've got unspecified as number two. So this is some sort of input error or maybe lack of information whenever the NYPD is taking down the contributing factor for a collision they're attending to. It's little bit concerning that it's so high, honestly.  

3. Calculate '% of Dangerous Collisions' for each contributing factor by taking the number of collisions with an injury or fatality and dividing them by the total

Right now, with the data that we have, there is no way that we can possibly calculate '% of Dangerous Collisions'. So we're going to have to go back to our source data and start adding some columns that will help us make those calculations in this pivot table. 

We added Dangerous column, using IF operator to define if the collision was dangerous, depending if some of the fsctors were 0 or 1. 

But we need '% of Dangerous Collisions', to do that we will add unitary column, which essentially means a column with just ones. 

![](/Traffic_Safety_Analysis/screenshots/adding_columns.png)

To calculate '% of Dangerous Collisions' we need to add calculated field:

![](/Traffic_Safety_Analysis/screenshots/calculated_field.png)

After all modification our PivotTable looks like this:

![](/Traffic_Safety_Analysis/screenshots/perc_dang.png)

4. Add data bars to the '% of Dangerous Collisions' values to visualize the results, and summarize the insights from your analysis

After applying conditional formatting to % Dangerous column our PivotTable looks like this:

![](/Traffic_Safety_Analysis/screenshots/cond_form_bars.png)

Insights:

We know that driver inattention and distraction is the main contributing factor in terms of number of collisions, but only 39% of those collisions are actually considered dangerous. 

Granted, it's not a tiny amount like Passing Too closely (11%), but it's not as high as the 64% of dangerous collisions occur whenever the contributing factor is the failure to lead right of way, which is the third most common. 

And if we don't count unspeccified, then it's the second most common. So maybe this is somewhere we have to focus on even before the driver inattention and distraction. 

And the same can go for traffic control disregarded in which 59% of the collisions are dangerous or unsafe speeds in which 46% of them are dangerous. 



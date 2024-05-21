## Visualize weekly trends

My second objective is to calculate the number of collisions by time of day and day of week, and visualize the data using a heatmap.

1. Extract the Weekday and Hour from the 'Date' and 'Time' columns

To extract the Weekday and Hour from the 'Date' and 'Time' columns we use Weekday and Hour functions:

![](/Traffic_Safety_Analysis/screenshots/weekday_hour.png)

2. Calculate the count of 'Collision ID' by Weekday and Hour

To calculate the count of 'Collision ID' by Weekday and Hour we insert PivotTable:

![](/Traffic_Safety_Analysis/screenshots/pivot_weekday.png)

3. Create a heatmap to visualize collision hotspots by time of day and day of week

![](/Traffic_Safety_Analysis/screenshots/heatmap.png)

4. Modify the heatmap to a "white-white-red" 3-color scale to keep focus on the most dangerous periods in the week and summarize the insights from your analysis

By editing the conditional formating rule we updated the heatmap for 3 scale format:

![](/Traffic_Safety_Analysis/screenshots/heatmap_updated.png)

We've got weekday collisions during 8:00 AM and kind of during nine. So when people are driving to work, then it cools off a little bit. And the we've gor lunch, which is most important or most impactful I guess. 

On Fridays we start to see colisions there.

And then during the 2:00 PM to 6:00 PM rush hour is when we really start to see the most collisions during the week, especially as the week goes on. 

So Monday isn't terrible, at least not compared to the rest.

There is more on Tuesdays then more on Wednesdays and more on Thursdays. 

And then the main pak from three to five on Fridays. 

And another hotspot that we can find is in midnight from Friday to Saturday, and from Saturday to Sunday. So during the weekends people are out, they're driving at night, maybe they're in no condition to be doing so. And once again, we have collision hotspots. 






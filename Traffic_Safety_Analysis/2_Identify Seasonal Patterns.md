## Identify Seasonal Patterns

My first objective is to calculate the number of collisions by month and year, and visualize them using line charts.

![](/Traffic_Safety_Analysis/screenshots/table_overview.png)

This is how table looks like before any modification and analysis.

We have 238,421 rows of data.

The date range is from 2021 till April,2023. 

![](/Traffic_Safety_Analysis/screenshots/date_range.png)

1. Calculate the count of 'Collision ID' by year and month, and visualize it using a line chart

To calculate the count of 'Collision ID' by year and month I will use PivotTable:

![](/Traffic_Safety_Analysis/screenshots/pivot.png)

Now let's visualize this table using a line chart:

![](/Traffic_Safety_Analysis/screenshots/line_chart.png)

We can see huge drop in April 2023. Why is that? That's because we don't have full month information. 

2. Filter out the incomplete month of April 2023

In order to solve the problem with incomplete month of April, we just drag date to filter field, unselect all the April 2023 dates, then our line chart looks like this:

![](/Traffic_Safety_Analysis/screenshots/solving_date_problem.png)

3. Modify the line chart so that each year is shown as a separate line

![](/Traffic_Safety_Analysis/screenshots/separate_years.png)

4. Apply formatting to finalize the chart and summarize insights from the analysis

![](/Traffic_Safety_Analysis/screenshots/final_line_chart.png)

It looks like the lines are kind of following the same shape. So there's a small drop off from January to February, then arise in March, and it continues to rise all the way up until the peak, not summer yet, but the warm months of May and June. Those tend to have the highest number of collisions, although it looks like it was a decrease from 2022 compared to 2021, which is positive. Hopefully we continue to see that in 2023, but again, after May and June, which are seem to be the peaks, there's a small drop off into July. It's stabilizes all the way up to September. Again, there's a small peak after that into October, and then it drops back in the colder month in November, December, and January. 

It does look like collisions in New York City follow a seasonal pattern, or at least that's working theory that we can form just based on this quick analysis.



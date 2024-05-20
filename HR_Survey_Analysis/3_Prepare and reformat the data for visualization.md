## Prepare and reformat the data for visualization

My second objective is to produce clean source data for visualization by calculating response frequencies and proportions for each of the 10 survey questions.

1. Create a new tab named Chart Source, and generate a unique list of survey questions

To generate a unique list of survey questions we gonna use UNIQUE function:

![](/HR_Survey_Analysis/screenshots/unique_questions.png)

So the result is the following:

![](/HR_Survey_Analysis/screenshots/unique_result.png)

2. For each question, calculate the count of records associated with each response type (1-4) and the average response, excluding zeros

To calculate the count of records associated with each response type (1-4) we use COUNTIFS function:

![](/HR_Survey_Analysis/screenshots/countifs1.png)

And to calculate the average response we use AVERAGEIFS function and add criteria "not equal" to zero:

![](/HR_Survey_Analysis/screenshots/averageifs.png)

3. Add new columns to convert the counts into percentages, based on the total responses for 1, 2, 3 or 4

![](/HR_Survey_Analysis/screenshots/counts_to_perc.png)

4. Copy and paste the data as values, then sort the questions descending by average response

After sorting questions descending by average repsonse our table is ready for visualization and looks like this:

![](/HR_Survey_Analysis/screenshots/resulting.png)



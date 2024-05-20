## Create calculated columns 

My first objective is to calculate top-level KPIs by flagging complaints as "Open" or "Closed" and creating a PivotTable to count the complaints for each status.

![](/Consumer_Complaint_Tracking/screenshots/table.png)

This is how our table looks like in the beginning.

The table contains 62,516 rows. 

The date range is between 2017 and 2023. 

![](/Consumer_Complaint_Tracking/screenshots/date_submitted.png)

1. Create a Status column that flags complaints as "Open" or "Closed" based on the values in the Company Response to Consumer column ("In progress" = "Open", others are "Closed").

If we check the possible values for Company reponse to consumer column, which are: Closed, Closed with explanation, Closed with monetary relief, Closed with non-monetary relief, In progress.

![](/Consumer_Complaint_Tracking/screenshots/consumer_compaints_resp.png)

So let's create new column "Status" that flags complaints as "Open" or "Closed" based on the values in the Company Response to Consumer column ("In progress" = "Open", others are "Closed"). For that we will use IF statement:

![](/Consumer_Complaint_Tracking/screenshots/open_closed.png)

This is the result of creating those flags:

![](/Consumer_Complaint_Tracking/screenshots/open_closed_result.png)

2. Create a Week start column with the date for the corresponding Monday of each Date received.

Let's create Week start column with the date for the corresponding Monday of each Date received. For that we will use Weekday function and to define beginning of the week we subtract this function from Date received column and add 1, so then we receive the beggining of the week:

![](/Consumer_Complaint_Tracking/screenshots/weekday.png)

The result of creating this column:

![](/Consumer_Complaint_Tracking/screenshots/weekday_result.png)

3. Extract the Year, Month, and Day of the Week start column.

Let's extract Year of the Week start column, by using Year function:

![](/Consumer_Complaint_Tracking/screenshots/year.png)

And Month, by using Month function:

![](/Consumer_Complaint_Tracking/screenshots/month.png)

And Day, by using Day function:

![](/Consumer_Complaint_Tracking/screenshots/day.png)

So the result of extracting is the following:

![](/Consumer_Complaint_Tracking/screenshots/result.png)

4. Change the formula for the Month column so that it returns the text for the month name in the “mmm” format (1=“Jan”, 2=“Feb”, etc.).

To change the formula for the Month column so that it returns the text for the month name in the “mmm” format we use TEXT function:

![](/Consumer_Complaint_Tracking/screenshots/mmm_format.png)

So the resulting table for Objective one:

![](/Consumer_Complaint_Tracking/screenshots/mmm_result.png)

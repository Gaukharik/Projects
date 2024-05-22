## Identify when vehicles are likely to be stolen

My first objective is to explore the vehicle and date fields in the stolen_vehicles table to identify when vehicles tend to be stolen.

Let's start by looking at the database:

![](/Motor_vehicle_thefts/screenshots/db_overview.png)

So we have 3 tables: locations, make_details and stolen_vehicles.

1. Find the number of vehicles stolen each year. What do the results tell you about the data set?

To answer the first question we are gonna look to stolen_vehicles table. 

This is the output of my first query:

![](/Motor_vehicle_thefts/screenshots/task1.png)

The table contains 8 columns: vehicle_id, vehicle_type, make_id, model_year, vehicle_desc, color, date_stolen and location_id.

So this gonna help me to find the number of vehicles stolen each year.

![](/Motor_vehicle_thefts/screenshots/num_veh.png)

That was the result of my query. We can see that 1668 vehicles was stolen in 2021 and 2885 in 2022. More vehicles were stolen in 2022. But where there actually more vehicles stolen? To figure this out, let's dive little bit deeper into the data. 

So I'm gonna find the number of vehicles stolen in each month.

2. Find the number of vehicles stolen each month. What insights can you gather from the results?

![](/Motor_vehicle_thefts/screenshots/month.png)

But we can see that that isn't all the months. So it looks like maybe our dataset contains data for a few month of the year. To confirm this let's modify our query:

![](/Motor_vehicle_thefts/screenshots/partial_months.png)

As we can see from output, we have partial data. So I have data for 2021, but just the last three months, and we only have four months of data for 2022. 

If we look at the number of vehicles stolen it seems that it's increasing this whole time, and then suddenly decreases at month four. 

So let's see what's happening there. Let's modify our query with WHERE statement. To break it down, I will also look at the day:

![](/Motor_vehicle_thefts/screenshots/breaking_day_4.png)

So we can see for the month of April that I only have six days worth of data. So that's why the count was so low. 

Let's look at our year and month breaking down:

![](/Motor_vehicle_thefts/screenshots/looking_again.png)

So looks like as the months go on, there are more and more vehicles stolen. And we have to remember that April is an anomaly, because we have six days worth of data. 

So one thing that we know is that in New Zeland, the summertime is the December to March months, and seems like there are more vehicles stolen as the summer goes on. 

So that's my conclusion from looking at the number of vehicles stolen each year and each month. 

3. Find the number of vehicles stolen each day of the week.

Let's now find the number of vehicles stolen each day of the week. So to do that, I can use the day of the week function:

![](/Motor_vehicle_thefts/screenshots/dow.png)

And we can see these were the number of vehiclesstolen each day of the week. 

This is kind of hard to interpret because these are numbers. So let's change these numbers into actual words. 

So that's what the next step is to replace the numeric day of week values with the full name of each day of the week. 

4. Replace the numeric day of week values with the full name of each day of the week (Sunday, Monday, Tuesday, etc.).

I can use CASE statement for this task:

![](/Motor_vehicle_thefts/screenshots/named_days.png)

So now here I have each day of the week by number, each day of the week by name and then the number of vehicles that were stolen on each day of the week. 

My next task is to create a bar chart. I can't do that in SQL, so I'm gonna export my data into a CSV file so that I can read that into Excel to create a data visualization. 

5. Create a bar chart that shows the number of vehicles stolen on each day of the week.

So this how our results from SQL looks like in Excel: 

![](/Motor_vehicle_thefts/screenshots/obj1_results.png)

So let's add our bar chart:

![](/Motor_vehicle_thefts/screenshots/bar_chart.png)

And for my surprise Mondays and then Tuesdays are the days with the most vehicle thefts in New Zeland. Then as the week goes on, it starts to drop through Wednesday, and then through Thursday we get a little bit a bump on Fridays. And then once again, it drops on Saturday and Sunday during the weekend. And then again we have that spike on a Monday. 

So that's a very interesting trend that I'm sure consumers will be very interested to know about. 
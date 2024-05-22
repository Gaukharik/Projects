## Identify which vehicles are likely to be stolen

My second objective is to explore the vehicle type, age, luxury vs standard and color fields in the stolen_vehicles table to identify which vehicles are most likely to be stolen.

1. Find the vehicle types that are most often and least often stolen

First let's look again to stolen_vehicles table: 

![](/Motor_vehicle_thefts/screenshots/stolen_veh.png)

As we can see we have vehicle_type column. This column we need to find the vehicle types that are most often and least often stolen.

![](/Motor_vehicle_thefts/screenshots/veh_type.png)

And we see here that these are the top five vehicles that are most commomnly stolen. Looks like station wagons are the ones that are most commonly stolen in New Zeland. 

Let's look at the ones that are least commonly stolen.

![](/Motor_vehicle_thefts/screenshots/least_stol.png)

We can see that these are pretty specialized vehicles that are not stolen as much. 

And so those are our most and least often stolen vehicles.  

2. For each vehicle type, find the average age of the cars that are stolen

Next, let's look at the average age of cars that are stolen. 

Let's first calculate the age of each car by subtracting model_year from date_stolen:

![](/Motor_vehicle_thefts/screenshots/age.png)

So now we can calculate the average age of each vehicle:

![](/Motor_vehicle_thefts/screenshots/avg_age.png)

I see here that these are now my vehicle types and this is the average age of all the vehicle types. 

Let's order descending by average age and see some insights:

![](/Motor_vehicle_thefts/screenshots/avg_ordered.png)

So on average they are less than 10 years old. So this is kind of interesting. It looks like newer tractors and mopeds are often stolen. 

3. For each vehicle type, find the percent of vehicles stolen that are luxury versus standard

If we look to our stolen_vehicles table again:

![](/Motor_vehicle_thefts/screenshots/table_ag.png)

I don't have an indicator here for which vehicles are luxury versus standard vehicles. So I'm gonna have to look somewhere else. 

So let's look at make_details table:

![](/Motor_vehicle_thefts/screenshots/make_det.png)

So we can see that we have make_type column where I have standard vehicles and luxury vehicles. 

So now let's find the percent of vehicles stolen that were luxury versus standard.

To do that I'm gonna join make_details and stolen_vehicles tables:

![](/Motor_vehicle_thefts/screenshots/joined.png)

So now I have one huge table. I have all my stolen vehicles data. 

So from here I need to calculate a percent. To calculate the percent first thing I'm gonna do is narrow down my data and then I'm gonna turn some of these text fields to numeric fields. So for this I only need a few fields. So I need vehicle type. I'm going just add vehicle type and make type. 

![](/Motor_vehicle_thefts/screenshots/narrowed.png)

To calculate the percent I need to change make_type field into a numeric field. 

I'm going to change what is luxury into one and everything that is standard to zero. I can do that by using CASE statement:

![](/Motor_vehicle_thefts/screenshots/luxury.png)

To calculate percentage I need to have numerator and denominator. So my numerator is gonna be the number of luxury vehicles and then my denominator is just gonna be if there's a vehicle or not.

![](/Motor_vehicle_thefts/screenshots/numerator.png)

We can see that now I have for each vehicle whether it's luxury or not. And then basically a one saying that this is vehicle. With this I can now group this data. 

![](/Motor_vehicle_thefts/screenshots/with_stat.png)

And now we can see for each vehicle type, the percent of vehicles that are luxury that were stolen. 

I'm going to order by percent luxe descending to see the vehicle types with the highest percent of luxury vehicles stolen:

![](/Motor_vehicle_thefts/screenshots/ordered_per.png)

Now we can see the that half of the convertibles stolen were luxury vehicles. So it's look like for convertibles and sport cars, there were a lot of luxury vehicles that were stolen.  

4. Create a table where the rows represent the top 10 vehicle types, the columns represent the top 7 vehicle colors (plus 1 column for all other colors) and the values are the number of vehicles stolen

I'm gonna have to take my dataset and then specify what I want as rows, specify what I want as the columns and then the values. And to do that I need to use CASE statements. 

![](/Motor_vehicle_thefts/screenshots/task4_stolen.png)

We have vehicle types and vehicle colors in this table. So from here, let's look at what those vehicle colors are, because we haven't looked into that yet:

![](/Motor_vehicle_thefts/screenshots/color.png)

I want top seven stolen colors. 

So with this I'm gonna have to create the table where the rows are vehicle types, the columns are these seven top colors, plus the 'other' field I'm gonna create. And then inside I want the values to be the number of vehicles stolen. To do that I'm gonna pivot my data using CASE statements. 

![](/Motor_vehicle_thefts/screenshots/top10.png)

Then we can see these are my top 10 most popular vehicles. 

5. Create a heat map of the table comparing the vehicle types and colors

For this question, we need to create a heat map. 

So I need to export this data to CSV file for that. 

![](/Motor_vehicle_thefts/screenshots/ob2_results.png)

This is the result from SQL, where we have top 10 types of vehicles by the number of total thefts. 

![](/Motor_vehicle_thefts/screenshots/heat_map.png)

And right off the bat we can see that 399 on Trailer kind of jumps out at us since it's the highest value. 

And it's particularly interesting because for these top three vehicle types, which are really small sedan type vehicles, the pattern for the colors really matches a pattern for the overall colors. 

We're kind of going from highest to the lowest, but for the triler, which is very unique type of vehicle, we have a huge value in silver. And then we have another big one in gray, which is really is very close to silver. 

And it's interesting because really while we see different colors in normal passenger vehicles with trailers you don't really get that much options. So right now it makes sense that the ones that are stolen the most are silver and gray, I guess most trailers are silver and gray. 

And the same thing happens for the boat trailer and the trailer-heavy. So really interesting trend. 

For Light Van and Utility we have some similar numbers. Most of them come in white color. 

And finally the values for Road bike and the Moped, which are very similar type of vehicles, but in this case, the ones that seem to draw the most attention from thieves are the black ones. 


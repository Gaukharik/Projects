## Identify where vehicles are stolen

My third objective is to explore the population and density statistics in the regions table to identify where vehicles are getting stolen, and visualize the results using a scatter plot and map.

1. Find the number of vehicles that were stolen in each region

We are going to look to stolen_vehicles table agian:

![](/Motor_vehicle_thefts/screenshots/obj3_task1.png) 

There is location_id, but there is no location details.

So to do that I have to look to locations table:

![](/Motor_vehicle_thefts/screenshots/locations.png)

And I see all the different regions in New Zeland, and also we have population and the density of each region. 

So to find the number of vehicles that were stolen in each region, I need to combine these two tables.

![](/Motor_vehicle_thefts/screenshots/joined_locations.png)

With this I can filter down and group this data. 

![](/Motor_vehicle_thefts/screenshots/region.png)

We can see for each region the number of vehicles that were stolen. 

2. Combine the previous output with the population and density statistics for each region

![](/Motor_vehicle_thefts/screenshots/population.png)

I see that most vehicles were stolen in Auckland, and then there were not very many vehicles stolen in Southland. And also we can see that Southland has a smaller population and is not very dense at all, where Auckland is extremely dense and has a lot of people. 

3. Do the types of vehicles stolen in the three most dense regions differ from the three least dense regions?

The first thing we need to do is figure out what the three most dense regions are and the three least dense regions.

![](/Motor_vehicle_thefts/screenshots/dense1.png)

So we can see that Auckland, Nelson and Wellington are three most dense regions. 

And our least dense regions are Otago, Gisborne and Southland.

Now that we have those I want to look at the types of vehicles that were stolen in these regions. 

![](/Motor_vehicle_thefts/screenshots/vehicle_types.png)

So for each vehicle type, I have the number of vehicles. 

Let's filter that data. 

![](/Motor_vehicle_thefts/screenshots/filtered.png)

And now we can see in the most densely populated areas, stationwagons, saloons and hatchbacks were the most common vehicle types that were stolen. 

So now, let's compare that with the less dense regions. 

![](/Motor_vehicle_thefts/screenshots/least_dense.png)

Then we can see the most common vehicles that were stolen were stationwagons, saloons and utility vehicles. 

I want to see these two queries both side by side. 

I can create a results table that contains both of them using a union. 

![](/Motor_vehicle_thefts/screenshots/union.png)

We can see the top five vehicles stolen in high density areas, and the top five vehicles stolen from in low density areas. So the roadbike make difference, because we can see it in high density areas, but not in low density areas. 

4. Create a scatter plot of population versus density, and change the size of the points based on the number of vehicles stolen in each region

The second query has all the data that we need for scatter plot. So we gonna export it to CSV file. 

So this how result table looks like in excel:

![](/Motor_vehicle_thefts/screenshots/obj3_results.png)

So let's create our bubble chart:

![](/Motor_vehicle_thefts/screenshots/bubble_chart.png)

![](/Motor_vehicle_thefts/screenshots/bubble_chart1.png)

Let's modify the axes:

![](/Motor_vehicle_thefts/screenshots/bubble_chart2.png)

We can see that Auckland has the largect population, the largest population density as well. And the most number of vehicles stolen, which makes sense. There are a lot of people, a lot of cars in a very small space, it makes sense to steal a lot of vehicles. 

But an interesting outlier here is Nelson, that has a very small population, a very high density, in fact, the second highest, but it doesn't have a lot of vehicle thefts compared to others like Wellington, Cantberry, Waikato and the Bay of Plenty. So it looks like the biggest driver in this case for vehicle thefts is population and not so much density. 

5. Create a map of the regions and color the regions based on the number of stolen vehicles

![](/Motor_vehicle_thefts/screenshots/map.png)

We can immediately see is very dark region, which is Auckland. So that's where we can really see just how dense the population has to be, because it is the most heavily populated region, but it is so small. So that's why we have the huge density and we can see by the color that it has the most number of vehicles stolen. 

After that it looks like it is Canterbury, which is confirmed by bubble chart. 

And then we've got some other regions like the Bay of Plenty. We have got Waikato. And the little tiny dot is Wellington. We can see it's higher than the rest in terms of density because of how small it is in terms of area, but it is still has quite a lot of vehicles stolen. 





## Profile & QA the data

My first objective is to explore and QA the data by calculating basic profiling metrics, removing blank and duplicate records, and standardizing inconsistent text fields.

This is how our table looks like before any data profiling:

![](/HR_Survey_Analysis/screenshots/table_overview.png)

The Status column contains either Complete or Incomplete values:

![](/HR_Survey_Analysis/screenshots/status.png)

The Department column contains some different departments:

![](/HR_Survey_Analysis/screenshots/department.png)

The columns from D till G shows if the staff member either Director, Manager, Supervisor or just Staff.

![](/HR_Survey_Analysis/screenshots/positions.png)

It looks like Question column contains 9 different questions, where question # 7 appears two times. This is something we gonna dive in deeper later:

![](/HR_Survey_Analysis/screenshots/questions.png)

In the Responses column there are some blank fields, which we figure out later:

![](/HR_Survey_Analysis/screenshots/responses.png)

The Response Text column also contains some blank fields:

![](/HR_Survey_Analysis/screenshots/response_text.png)

1. Calculate the minimum, maximum, count, and number of blanks for each numerical field

![](/HR_Survey_Analysis/screenshots/max_min_count.png)

The count of Response column is bit lower than other counts. And the reason it's lower is because we're registering 135 blanks in that range.

2. Remove any records with blank responses

To remove records with blank responses we just filter the Response column by Blanks value and delete those rows:

![](/HR_Survey_Analysis/screenshots/obj1_task2.png)

So after deleting those rows with blanks values we don't have any blanks in Response column:

![](/HR_Survey_Analysis/screenshots/obj1_task2_result.png)

3. Remove any records containing duplicate values across all fields

To remove duplicates we select entire dataset and choose "Remove Duplicates" option in Data tab:

![](/HR_Survey_Analysis/screenshots/removing_dupliates.png)

4. Calculate the count or frequency of each value in the Department and Question fields, and standardize any inconsistencies you find

To calculate the count or frequency of each value in the Department field we can create PivotTable:

![](/HR_Survey_Analysis/screenshots/department_pivot.png)

There are no duplicates or missing values here.

From frequency points we get a lot of responses from employees in the Planning and Public works Department.

To calculate the count or frequency of each value in the Question field we can also use the PivotTable:

![](/HR_Survey_Analysis/screenshots/question_pivot.png)

But we can see some weird stuff here. I'm seeing two instances of question 10, whick look identical. We've got two instances of question 7 as well. 

So let's dig in a little bit deeper and see what's going on here.

If I look to question 7 I can see the difference is that one version of the question uses an ampersand, the other uses the word. To solve this we can just replace & with and in dataset:

![](/HR_Survey_Analysis/screenshots/find_replace.png)

So after refreshing PivotTable, this mistake gone:

![](/HR_Survey_Analysis/screenshots/find_replace_result.png)

But what about question 10? It's invisible trailng space. 

To solve this we use TRIM Function:

![](/HR_Survey_Analysis/screenshots/trimming.png)

So now our PivotTable looks fine:

![](/HR_Survey_Analysis/screenshots/cleaned.png)




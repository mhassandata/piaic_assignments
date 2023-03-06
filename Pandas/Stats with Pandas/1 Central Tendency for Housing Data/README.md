LEARN STATISTICS WITH PYTHON
Variance in Weather
You’re planning a trip to London and want to get a sense of the best time of the year to visit. Luckily, you got your hands on a dataset from 2015 that contains over 39,000 data points about weather conditions in London. Surely, with this much information, you can discover something useful about when to make your trip!

In this project, the data is stored in a Pandas DataFrame. If you’ve never used a DataFrame before, we’ll walk you through how to filter and manipulate this data. If you want to learn more about Pandas, check out our Data Science Path.



Explore the Data
1.
All of the weather data is stored in a variable named london_data.

Print the first few rows of the dataset by calling print(london_data.head()).

Take a look at the browser to see the columns of this dataset. Here are two questions to ask yourself:

How often were measurements taken?
Which columns might be the most useful when thinking about planning a trip.
If you want to see different rows of the data, you can try something like this:

print(london_data.iloc[100:200])
This will print rows 100 through 199.

Comment out these print statements after looking through the results.


2.
Let’s also take a look at how many data points we have. Print len(london_data)


3.
Now that we’ve seen what the data looks like, let’s dive into one of the more promising columns — "TemperatureC". This column stores the temperature in Celsius.

To get a single column from a DataFrame, you can use this syntax:

one_column = london_data["column_name"]
Create a variable named temp and set it equal to the "TemperatureC" column of london_data


4.
We can now calculate descriptive statistics about this column. To begin, find the average temperature in London in 2015. Store it in a variable named average_temp.


5.
Calculate the variance of the temperature column and store the results in the variable temperature_var. Print the results.


6.
Calculate the standard deviation of the temperature column and store a variable named temperature_standard_deviation. Print this variable.

How would the variance and standard deviation help you plan a trip?


Filtering By Month
7.
The statistics we just calculated aren’t very helpful when trying to plan a vacation since they describe the weather throughout an entire year.

If we could find a way to use the rows from only a certain month, that might help us find the best month to plan our trip.

Once again, print london_data.head() to see the first few columns of our DataFrame. Which column will help us get only the data points from January? In the browser you can scroll to the right to see more columns.


8.
We want to filter by the "month" column! The following line of code will create a variable that gets the temperature from the rows where "month" is 6. These will be all of the rows from the month of June.

june = london_data.loc[london_data["month"] == 6]["TemperatureC"]
Create this variable for June.

9.
Create a variable named july that contains all of the data points from July. The code to do this should look very similar to your code that created the June variable. This time, we’re interested in month 7.


10.
Calculate and print the mean temperature in London for both June and July using the np.mean() function.

What do these numbers tell you? If you wanted to visit London on the month that was, on average, cooler, which month would you pick? Look at the hint to see our thoughts!

11.
Calculate and print the standard deviation of temperature in London for both June and July. Remember, the function you should use is np.std().

What do these numbers tell you? How might the standard deviation change your decision on when to visit London? Click on the hint to see our thoughts.

12.
If you want to quickly see the mean and standard deviation of every month, use this block of code.

for i in range(1, 13):
  month = london_data.loc[london_data["month"] == i]["TemperatureC"]
  print("The mean temperature in month "+str(i) +" is "+ str(np.mean(month)))
  print("The standard deviation of temperature in month "+str(i) +" is "+ str(np.std(month)) +"\n")
During which month would you most like to visit? If you wanted to pick the month with the least variable temperature, which one would you pick?

Explore on Your Own
13.
By looking at the mean and standard deviation of the temperature in London during each month of the year, we can get a sense of the best time to visit.

Looking at the spread of the data is an important statistic to consider if you are particularly sensitive to extreme days. For example, if you pick a month with a large standard deviation, you might have one day that is relatively cold while the following day is very hot.

Take some time to see if you can find more insights in this dataset. Here are some ideas we have for you:

Look at columns other than "TemperatureC". Can you find something interesting about the humidity or the air pressure? Can you find the rainiest month? London is notoriously rainy!
Filter based on"hour". Similar to how you filtered based on the month, are there certain hours that have higher variance than others?

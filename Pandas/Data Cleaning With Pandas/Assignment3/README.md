LEARN STATISTICS WITH PYTHON
Life Expectancy By Country
Over the course of the past few centuries, technological and medical advancements have helped increase the life expectancy of humans. However, as of now, the average life expectancy of humans varies depending on what country you live in.

In this project, we will investigate a dataset containing information about the average life expectancy in 158 different countries. We will specifically look at how a country’s economic success might impact the life expectancy in that area.


Access the Data
1.
We’ve imported a dataset containing the life expectancy in different countries. The data can be found in the variable named data.

To begin, let’s get a sense of what this data looks like. Print data.head() to see the first 5 rows of the dataset.

Look at the names of the columns. What other pieces of information does this dataset contain?

You may want to comment out this print statement after looking at the data.

2.
Let’s isolate the column that contains the life expectancy and store it in a variable named life_expectancy. To get a single column from a Panda DataFrame, use this syntax:

single_column = dataFrameName["columnName"]
Make sure to pay attention to capitalization and spaces when using the column name!

Find the Quantiles
3.
We can now use NumPy functions on that column! Let’s use the np.quantile() function to find the quartiles of life_expectancy. Store the result in a variable named life_expectancy_quartiles and print the results.

4.
Nice work! By looking at those three values you can get a sense of the spread of the data. For example, it seems like some of the data is fairly close together — a quarter of the data is between 72.5 years and 75.4 years.

Could you predict what the histogram might look like from those three number? Plot the histogram by using the following two lines of code. Does it look how you expected?

plt.hist(life_expectancy)
plt.show()

5.
Let’s take a moment to think about the meaning of these quartiles. If your country has a life expectancy of 70 years, does that fall in the first, second, third, or final quarter of the data?

Click on the hint to see the answer!

Splitting the Data by GDP
6.
GDP is a mesaure of a country’s wealth. Let’s now use the GDP data to see if life expectancy is affected by this value.

Let’s split the data into two groups based on GDP. If we find the median GDP, we can create two datasets for “low GDP countries” and “high GDP countries.

To start, let’s isolate the GDP column and store it in a variable named gdp. This should be similar to how you isolated the life expectancy column.

7.
We now want to find the median GDP. You can use NumPy’s np.median() function, but since the median is also a quantile, we can call np.quanitle() using 0.5 as the second parameter.

Store the median in a variable named median_gdp. Print that variable to see the median.


8.
Let’s now grab all of the rows from our original dataset that have a GDP less than or equal to the median. The following code will do that for you

low_gdp = data[data['GDP'] <= median_gdp]
Do the same for all of the rows that have a GDP higher than the median. Store those rows in a variable named high_gdp.

The line of code should look almost identical to the one above, but you should change the <= to >.

Remember to change the name of the variable!

9.
Now that we’ve split the data based on the GDP, let’s see how the life expectancy of each group compares to each other.

Find the quartiles of the "Life Expectancy" column of low_gdp. Store the quartiles in a variable named low_gdp_quartiles. Print the results.
10.
Find the quartiles of the high GDP countries and store them in a variable named high_gdp_quartiles. This should look very similar to the last line of code you wrote. Print the results.



Histogram and Conclusions
11.
By looking at the quantiles, you should get a sense of the spread and central tendency of these two datasets. But let’s plot a histogram of each dataset to really compare them.

Remove the two lines of code that are currently plotting the histogram of the original dataset. At the bottom of your code, add these four lines:

plt.hist(high_gdp["Life Expectancy"], alpha = 0.5, label = "High GDP")
plt.hist(low_gdp["Life Expectancy"], alpha = 0.5, label = "Low GDP")
plt.legend()
plt.show()
12.
We can now truly see the impact GDP has on life expectancy.

Once again, consider a country that has a life expectancy of 70 years. If that country is in the top half of GDP countries, is it in the first, second, third, or fourth quarter of the data with respect to life expectancy? What if the country is in the bottom half of GDP countries? Check the hint to see our thoughts.

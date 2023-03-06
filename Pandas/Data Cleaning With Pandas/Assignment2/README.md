LEARN STATISTICS WITH PYTHON
Healthcare in Different States
In this project, we will use boxplots to investigate the way hospitals in different states across the United States charge their patients for medical procedures.

This dataset might look a bit familiar to you — we used it in our lesson about describing histograms. The data originally came from the United State Health and Human Services Department.

Let’s use boxplots to find more meaning in this data!



Investigate the Data
1.
We’ve imported the dataset into a variable named healthcare. Let’s take a look at what data we have to work with. Print healthcare.head(). This will print the first five rows of the dataset.

Scroll through the table to see what information we have. We know that we want to eventually look at the way heathcare works in different states. What column will be useful to do that?

Note that we’re going to ask you to print out multiple values over the course of the project. Feel free to comment out old print statements using # to avoid clutter:

# This is a comment

Investigate the Data
1.
We’ve imported the dataset into a variable named healthcare. Let’s take a look at what data we have to work with. Print healthcare.head(). This will print the first five rows of the dataset.

Scroll through the table to see what information we have. We know that we want to eventually look at the way heathcare works in different states. What column will be useful to do that?

Note that we’re going to ask you to print out multiple values over the course of the project. Feel free to comment out old print statements using # to avoid clutter:

# This is a comment



3.
Let’s grab only the rows in the dataset that are about chest pain. Use this line of code to do that.

chest_pain = healthcare[healthcare['DRG Definition'] == '313 - CHEST PAIN']
If you’re interested in investigating a different diagnosis, replace '313 - CHEST PAIN' with the name of the other diagnosis. You might want to change the new variable name to be something other than chest_pain if you do this!

Separating By State
4.
We now want to separate the dataset by state. Eventually, we’ll use a for loop to do this for every state, but for now, let’s prove to ourselves that we can make a boxplot for one state.

When we printed the head, we saw the first few rows had a 'Provider State' of "AL". Those were hospitals in Alabama.

To get every chest pain diagnosis in Alabama, use this line of code:

alabama_chest_pain = chest_pain[chest_pain['Provider State'] == "AL"]
Make sure to use the variable that you created in the previous step. We called it chest_pain, but you might have named it something else if you used a different diagnosis.

Again, feel free to use a state of your choosing instead of Alabama. Different state abbreviations should work, like "CO" or "NY". Name your variable appropriately!

5.
We’re almost there! We now have all of the hospitals in Alabama that have a diagnosed chest pain. We now want to find the average cost of those diagnoses. These value is stored in the column ' Average Covered Charges ' (Note the spaces at the start and the end of the string!)

To get only these values, call this line of code:

costs = alabama_chest_pain[' Average Covered Charges '].values
Again, make sure that you’re using the correct variable names — yours might be different.

6.
Let’s now make a boxplot of those values! Call plt.boxplot() using costs as the first parameter.

Then call plt.show() to see your boxplot!

3.
Let’s grab only the rows in the dataset that are about chest pain. Use this line of code to do that.

chest_pain = healthcare[healthcare['DRG Definition'] == '313 - CHEST PAIN']
If you’re interested in investigating a different diagnosis, replace '313 - CHEST PAIN' with the name of the other diagnosis. You might want to change the new variable name to be something other than chest_pain if you do this!

Separating By State
4.
We now want to separate the dataset by state. Eventually, we’ll use a for loop to do this for every state, but for now, let’s prove to ourselves that we can make a boxplot for one state.

When we printed the head, we saw the first few rows had a 'Provider State' of "AL". Those were hospitals in Alabama.

To get every chest pain diagnosis in Alabama, use this line of code:

alabama_chest_pain = chest_pain[chest_pain['Provider State'] == "AL"]
Make sure to use the variable that you created in the previous step. We called it chest_pain, but you might have named it something else if you used a different diagnosis.

Again, feel free to use a state of your choosing instead of Alabama. Different state abbreviations should work, like "CO" or "NY". Name your variable appropriately!

5.
We’re almost there! We now have all of the hospitals in Alabama that have a diagnosed chest pain. We now want to find the average cost of those diagnoses. These value is stored in the column ' Average Covered Charges ' (Note the spaces at the start and the end of the string!)

To get only these values, call this line of code:

costs = alabama_chest_pain[' Average Covered Charges '].values
Again, make sure that you’re using the correct variable names — yours might be different.

6.
Let’s now make a boxplot of those values! Call plt.boxplot() using costs as the first parameter.

Then call plt.show() to see your boxplot!

8.
We’ll now use a for loop to separate the dataset into a dataset for each state:

datasets = []
for state in states:
  datasets.append(chest_pain[chest_pain['Provider State'] == state][' Average Covered Charges '].values)
datasets now contains 50 datasets — one for each state.

9.
We’re about to draw 50 boxplots. Before we draw them, let’s make sure there’s enough room. Call plt.figure(figsize=(20,6)). This will make your figure long to allow room for so many boxplots!

10.
Draw the boxplot using datasets as the first parameter. Add the second parameter labels = states to label your boxplots.

Finally, make sure to call plt.show().


Interpret and Explore
11.
Nice work! You should now see 50 boxplots. If the graph is too small to see, you can expand it by clicking on the arrows in the top right corner of the right panel. You can also take a look at this image to see what your final results should look like.

What information have you learned by looking at these boxplots side by side? What state has the largest spread? What state has the largest median? Which states have the most outliers?

Check the hint to see our thoughts.

Interpret and Explore
11.
Nice work! You should now see 50 boxplots. If the graph is too small to see, you can expand it by clicking on the arrows in the top right corner of the right panel. You can also take a look at this image to see what your final results should look like.

What information have you learned by looking at these boxplots side by side? What state has the largest spread? What state has the largest median? Which states have the most outliers?

Check the hint to see our thoughts.

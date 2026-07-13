****
Coffee Shop Sales: Guided Data Analysis Python Project
****
Phase 1: Explore the Data

The first rows of the dataset indicate that it is made of a range of data types, such as integers, floats and strings. Even formats such as dates and times are included. These may need to be simplified when the data is cleaned. 
There are 3547 entries/rows in the dataset, and 11 columns. All column names are string data types. 
A quick look at the descriptive statistics for the integer/float columns shows that the mean amount of money spent is 31.65, and that the coffee shop appears to be selling drinks between 6am and 10pm. 
Happily, there are no missing values in the entire dataset. 

Phase 2: Basic Business Insights

From some simple commands, I can see that 3547 sales have  been recorded in this dataset. These span from a date range between 1st March 2024 and 23rd March 2025. 
By searching for unique values in the "coffee_name" column, I find that there are 8 different types of drink sold here. These include latte, hot chocolate and cappuccino. 
By counting the values in the "coffee_name" column, I find that the americano with milk is the drink with most sales, with 809 sales made within the time period. The espresso has made the least sales, with 129 sales made within the time period. 
Interestingly, all 3547 sales have been made with a card - no cash sales whatsoever. 

Phase 3: Advanced Insights with Pandas

I used groupby() and obtained the total revenue of each type of drink by combining information from the "coffee_name" and "money" columns. This shows me that latte generates the highest revenue at 26875.30, followed by americano with milk which generates the second highest revenue at 24751.12. To improve the output, I turned the series into a dataframe, and I ordered the dataframe from lowest to highest revenue. 
I also found the average spend for each drink type - interestingly, the highest average spend was for hot chocolate (35.9), even though latte generates the most revenue. However, this is probably because hot chocolate was only the 6th highest selling drink, as opposed to latte, which was the 2nd highest selling drink. 
I found that the revenue is highest on Mondays and Tuesdays, and lowest on Saturdays and Sundays. This might be because of a higher number of commuters buying coffees during the weekday. 

Phase 4: Data Visualisation

First, I determined the popularity of drinks and made a countplot of the sales by drink type using Seaborn - it is clear to see that americano with milk and latte are the highest selling drinks. This makes the result from value_counts() easier and quicker to understand. To improve readability, clarity and communication, I added informative axes labels and a plot title, and I also used a coffee colour for the bars. I also added bar labels to the end of each bar and switched the axis to avoid overlapping coffee names.

Next, I determined the drinks responsible for generating the highest revenue. Creating a quick series of the results highlights the important insight - that latte generates the most revenue, but americano with milk is the most popular drink. This is because latte is more expensive than americano with milk, and suggests number of sales alone do not determine success in revenue. I created a barplot using seaborn showing the total revenue of each drink ordered from highest to lowest. This time, I kept coffee names on the x axis and applied a small rotation to avoid overlap. 

Lastly, I determined whether there is higher customer footfall on certain days of the week compared to others. I created another countplot on seaborn, and used the weekday column from the dataset. There are slightly more transactions made on Monday and Tuesday, and slightly less made on Saturday and Sunday. A suggestion might be to introduce more offers and promotions on quieter days to increase number of transactions, or to increase staffing on busier days to keep up with customer demand. 

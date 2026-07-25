****
**Netflix Film and TV Data Analysis - Non-Guided**
****
Introduction:
As one of the worlds largest and most popular streaming platforms, Netflix contains content from a vast range of nationalities and eras in the form of both TV shows and movies. With thousands of entries available to view on the platform, it is useful to identify the trends and common patterns behind the information on Netflix, to better understand the consumer needs and wants. 

My primary source was a Kaggle Netflix dataset with over 7000 entries. I investigated some key business questions related to the genres and origin countries of the content, as well as the distribution of content over time and common themes in the content. To do so, I used EDA, data gathering to form insights and a range of python libraries to create visualisations (matplotlib, seaborn, pandas, wordcloud). 

Phase 1: Data Cleaning and Exploratory Data Analysis

I begin by importing the necessary libraries; pandas, numpy, seaborn and matplotlib. I read in the csv.file and check the first 10 lines of the data. At a glance, there are a few missing data points in a few of the columns, the dataframe contains lots of information about films and TV shows from many different countries. The dataframe includes informative column names. I can see that there are 7787 rows and 12 columns, and I can see the "director", "cast" and "country" columns contain a large number of missing values, however, there are no duplicated entries. 

Next, I checked the summary statistics of the database with "describe()". At a glance, I can see that Raul Campos and Jan Suter have directed 18 titles in the database, David Attenborough is cast in 18 titles in the database, and 118 titles were added to Netflix on 1st January 2020 - this was clearly a popular date for new additions to Netflix! I learned there are over 400 unique types of genre in the database - with a large number of these only appearing once, and Documentaries appearing over 300 times. By using .head() for types of genre, I can see that the genre column contains multiple combined types, so this column must be separated to obtain a more accurate idea. 

Phase 2: Business Questions and Basic Visualisations

What percentage of Netflix's catalogue consists of movies vs TV shows? 
- Movies make up almost 70% of the total catalogue, this is a much higher proportion of entries than TV shows (at only 30%). However, it is worth remembering that TV shows will make up a longer duration overall when compared to movies depending on the number of episodes they contain. The pie chart represents this split between movie and TV shows for clarity. Thus, we can see that the vast majority of content on Netflix is movies. 

Which genres are best represented and which may benefit from further representation?
- As mentioned earlier, the genre column consists of multiple types of genre assigned to each entry. This makes it difficult to obtain an accurate idea of how many times each genre appears in the database. I used .str.split.explode() and .value_counts() on the "genres" column to separate each type and count the number of times it appears in the database. Now, it is clear that International Movies (2437) takes the  top spot, not Documentaries (786) as it originally appeared. I created variables of the top and bottom 10 types of genre, and created 2 barplots expressing these genres visually. It is clear that International Movies, Dramas and Comedies are very well represented on Netflix, whereas Thrillers, Classic and Cult TV might benefit from further representation. 

What countries are the highest contributors of content?
- I used value_counts to store the number of times each country appears in the "country" column and plotted the top 5 contributors in a barplot. The USA is by far the highest contributor, followed by India and the UK. These countries are clearly invested in significantly more than any other country to be producing such vast quantities of content. 

Phase 3: Further Insights and Visualisations

Heatmap to identify seasonal trends of content added by month and year:
- I converted the date_added column into the datetime type and created 2 sub-columns for month and year. This will make up the information in my heatmap, together with the show_id column from the Netflix database. I created a pivot table with this information and used this to create a heatmap displaying the content added to Netflix over months and years between 2008 - 2021. The heatmap shows no obvious seasonal trends, but it is clear there has been a massive influx of content after 2016, and that the most popular month for content to be added to Netflix was in November 2019. There are more purple areas throughout 2017 and 2018, and more pink/orange areas throughout 2019 and 2020. This suggests an increase in popularity of Netflix after the pandemic. There is no data after January 2021, so this explains the 0 values in the pivot table and heatmap after this date. 

Wordcloud of most common/frequent keywords in the description - are there popular ideas in the content or areas to invest more into?
- First, I joined all the descriptions from the database into one long variable, separated by a space. I used the STOPWORDS module to remove everyday words that are meaningless to the analysis. Before applying it, I added a few more words I thought common to Netflix descriptions to make the analysis more meaningful. My resulting wordcloud indicated the most frequent words to be "life", "family", "love" and "new". This suggests content related to the journey of life taken amongst loved ones is particularly resonant with viewers, and appears to be a common theme which describes the content on Netflix. Although the wordcloud does not provide particular quantitative analysis of the dataset, it provides a high-level summary of popular themes and language used in the dataset and this is helpful when understanding areas of interest for the audience. 

Conclusions:

It is clear from the data that movies represents a much higher proportion of the content than TV shows. The most dominant genres are International Movies and Dramas, with a potential for further investment in less represented genres such as Classic TV and Thrillers. The major content-producing countries are the USA, India and the UK. The amount of content added to the catalogue has increased in recent years, between 2019-2021, when compared with before 2018. There is no definite revelation of seasonal trends throughout the year, but content added is increasing on a year-to-year basis. 

This catalogue is not an exhaustive dataset and only represents data between 2016 and 2021. Although the wordcloud highlights common themes in the content, this is not a representation of the more/less successful items on Netflix, and is intended to show the more frequent language used by the platform when describing its content to viewers. 

![Google Play Store GIF](https://miro.medium.com/v2/resize:fit:1400/1*Fs7bWymmP_C_PAimpacmCw.gif)

# Introduction
The Google Play Store hosts a vast number of applications spanning diverse categories, attracting millions of user reviews. Understanding the dynamics of these apps and their user feedback can provide valuable insights for developers and stakeholders. This project aims to analyze the applications available on the Google Play Store along with the sentiment of user reviews. By leveraging various data analysis and visualization tools, the project seeks to uncover patterns and trends that can enhance the overall user experience and optimize app development processes. The insights derived from this analysis will help in making informed decisions to improve app quality, user satisfaction, and market strategies.

# Objectives
The objective of this project is to gain insights into the applications hosted on Google Playstore and the sentiment of their user reviews and present these insights in the form of visualisation which can be used to improve the overall experience and optimise the application development processes.
# Tools Used
- Microsoft Excel
- Google Colab (Python libraries - Numpy, Pandas, Seaborn, Matplotlib, TextBlob)
- MySQL Workbench
- PowerBI
# Project Files Description
Data Source : **Kaggle**

**playstore_apps.csv** - It contains the basic details of the app like number of user reviews, ratings, etc.

- App: It contains the name of the app with a short description (optional).
- Category: This section gives the category to which an app belongs. In this dataset, the apps are divided among 33 categories.
- Size: The disk space required to install the respective app.
- Rating: The average rating given by the users for the respective app. It can be in between 1 and 5.
- Reviews: The number of users that have dropped a review for the respective app.
- Installs: The approximate number of times the respective app was installed.
- Type: It states whether an app is free to use or paid.
- Price: It gives the price payable to install the app. For free type apps, the price is zero.
- Content rating: It states which age group is suitable to consume the content of the respective app.
- Genres: It gives the genre(s) to which the respective app belongs.
- Last updated: It gives the day in which the latest update for the respective app was released.
- Current Ver: It gives the current version of the respective app.
- Android Ver: It gives the android version of the respective app.
**playstore_reviews.csv** - It contains the user reviews for respective app.

- App: It contains the name of the app with a short description (optional).
- Translated_Review: It contains the English translation of the review dropped by the user of the app.
# Steps Involved
Data Cleaning and Transforming
To prepare the data for analysis, we performed several data cleaning steps. First, we checked for null values to ensure that there were no missing pieces of data. We also identified and removed outliers, especially in cases where ratings had a specific range. If null values existed and needed to be replaced with some value, we inserted values using the modeValue method. We modified data values, for size column we removed symbols like K and M and replaced them with their respective values, as well as removed unwanted characters like "+" and ",". We changed data types of columns to ensure that the data was in a format that was easy to analyze. Finally, we dropped duplicates and checked unique values to ensure the integrity of the data and that it was compliant with the intended datatype. A new column 'Revenue' was added by multiplying the prices and installs value for each record.
# Sentiment analysis using Natural Langugage Processing
We performed sentiment analysis on Google Play Store reviews using NLP and TextBlob.The analysis is based on three metrics: polarity, subjectivity, and sentiment. The polarity column indicates the sentiment of each review as positive, negative, or neutral. The subjectivity column measures the degree of personal opinion in the review on a scale of 0 to 1, where 0 represents a factual statement and 1 represents a highly opinionated statement. The sentiment column is an aggregate score between -1 and 1 that takes into account both polarity and subjectivity. A score of -1 indicates an extremely negative review, 1 indicates an extremely positive review, and 0 indicates a neutral review. These insights can be useful for improving product quality and customer satisfaction.
# Insights using MySQL
A schema was created having both the datasets to answer the problem statements through queries in MySQL Workbench.


- Problem Statements-

1. Total number of apps present in the Google playstore dataset.
2. Number of Categories present in the dataset.
3. All categories with the number of apps in them.
4. Average rating and average size of all the apps.
5. Overview of all categories wrt Number of installs, least rated app, highest rated app, number of free apps and number of paid apps in that category in that category.
6. Which are the top 10 highest rated apps in the given available dataset?
7. What are the number of installs and reviews for the above apps? Return the apps with the highest reviews to the top.
8. Which app has the highest number of reviews? Also, mention the number of reviews and category of the app.
9. What is the total amount of revenue generated by the google play store by hosting apps? (Whenever a user buys apps from the google play store, the amount is considered in the revenue)
10. Which Category of google play store apps has the highest number of installs? Also, find out the total number of installs for that particular category.
11. Which Genre has the most number of published apps?
12. Find the count of apps in each content rating based on App type.
13. Create a new column to bucket rating to high(4-5), medium(2-4), low(0-2). Return the app names.
14. Return categories with their sentiment counts for each type of sentiment.
15. Provide the list of all games ordered in such a way that the game that has the highest number of installs is displayed on the top.
16. List all non-entertainment and non-education apps that are rated by everyone or teen.
17. List all the apps whose app names contain the letter “i” or start with the letter “D”
18. Return the app names, categories, sizes, release dates (rename it to “Last Updated”) of apps whose app names have more than 1 word, and whose categories are music and social, and whose sizes are bigger than 10. Order the output result by maximum installs in descending order, then release dates in ascending order.
19. Find the number of apps in each category that have a rating greater than the average rating.
20. List the largest app size within each app category.
Data Visualization
Visualization was done in:
• Python- using Matplotlib and Seaborn libraries in Google collab

• Power BI- Major part of visualization was done here after loading the cleaned datasets.

Please refer to PowerBI Reports.pdf for python visualisations on the 4th page:
*****
Here, we divided our analysis into 3 parts:
- **Category wise analysis**: Top categories, Content rating distribution, Average rating of categories, Revenue, Average app size per category, Sentiment distribution across all categories.
- **Applications wise analysis**: An overview of all applications with different parameters, Bar plots for Installs, Ratings, Revenue, Reviews and Size.
- **Sentiment analysis of user reviews**: Sentiment count by category, Top 5 most positively and negatively reviewed categories and Subjectivity distribution across categories:
0-0.25 ~ Factual opinion
0.25-0.5 ~ Moderately factual
0.5-0.75 ~ Moderately personal
0.75-1 ~ Personal opinion

# Challenges Faced
- The Amount of Null values in the dataset were very high and had to be dropped while cleaning which took out almost 13.75% of the dataset, the integrity of the dataset was weak which lead to dropping 1491 rows just to remove Null values.
- The combined dataset after joining in SQL of both Playstore Apps and user reviews had only 500 apps in common, which accounts for merely 6.1 % of the total cleaned data. With a larger overlap of around 70% - 80% between the datasets, we could have derived more meaningful insights and conducted more valuable analysis.

- Many of the applications had their names containing only symbols and invalid characters, we found that those applications didn’t exist on the Google Playstore so we these applications had to be removed from the analysis.

# Conclusion
There are total 33 categories and 8158 applications in the given dataset with an overall average rating of 4.2 and an average application size of 19.38 MB.
For content rating, majority of the applications fall under ‘Everyone’ followed by ‘Teen’ and ‘Mature17+’. The least being ‘Adults only 18+’ and Unrated.
Majority of the apps, 92.06% are listed as free while only 7.94% being of paid type. ‘Family’ followed by ‘Game’ have the highest number of paid apps.
‘Family’ is the top category with the highest number of applications followed by ‘Game’ while ‘Beauty’ and ‘Comics’ being the lowest.
While ‘Family’ is the top category, it lags behind in revenue. ‘Lifestyle’ made the highest revenue followed by ‘Game’ and ‘Family’ while ‘Comics’ and ‘House and home’ made the least revenue.
‘Events’ is the top category with the highest average rating of 4.45 followed by ‘Education’ and ‘Art and design’.
‘Google news’ and ‘Subway surfers’ are the most popular apps in terms of installs with 1000M installs.
‘I am rich’ is the highest earning app followed by it’s premium version and ‘Hitman Sniper’.
Clash of Clans, Subway Surfers and Clash Royale are the most reviewed apps with 44 million+ reviews.
The largest app on the Play Store is ‘Hungry Shark Evolution’ belonging to ‘Game’ category with 95.37 MB.
The total number of reviews are 37,427 out of which 19,222 are of Free apps and 225 reviews are of Paid apps.
Majority of the reviews have a positive sentiment followed by Negative and Neutral.
‘Game’ has the highest number of reviews when it comes to Positive and Negative Sentiments followed by ‘Family’.
Sentiment Subjectivity is directly proportional to sentiment polarity in maximum reviews.
40.02% of the Total reviews are Moderately Personal, followed by Moderately Factual at 27.54% and then by Factual Opinion at 16.53% and 15.90% are Personal Opinion.
Bivariate analysis of the following present some deeper insights as depicted -

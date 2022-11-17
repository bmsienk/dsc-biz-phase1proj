# dsc-biz-phase1proj

## 1

## 2

## Comparison with Budget and Gross

The final step in the process was to compare various metrics from the IMDB SQL database with metrics for the production budget and total gross from the Numbers CSV file. The first step in the process required cleaning the two dataframes to have a matching size and then finally merging them into a final data frame to conduct an analysis. This process first required creating a unique identifier for both of the dataframes and cleaning them based on the movies present in both dataframes. The most obvious unique identifier to use as movie title plus release year. This narrowed down both dataframes and, after removing some duplicates from the IMDB dataframe, allowing them to be merged resulting in the table below.
    
![Merged TN and IMDB tables](images/df_analysis_table.png "Merged TN and IMDB tables")
    
The following table was also required to analyze the budget vs. total gross. This table was favored to the previous as it contains more data points. The table below shows the cleaned version.
    
![Cleaned TN Table](images/tn_df_table.png "Cleaned TN Table")
    
The final step was to do some final formatting for clean modeling. This required writing a function to remove $ and , from the relevant columns and also divided by one million for cleaner-looking visualizations. With the data ready for visualization and analysis, the correlation tables were generated, as seen below.
    
![Merged TN and IMDB correlation table](images/df_analysis_corr.png "Merged TN and IMDB correlation table")
    
![TN correlation Table](images/tn_df_corr.png "TN correlation Table")
    
The first obvious question to answer from the merged data set was, "Does production budget affect average rating?" The first metric to analyze here is the correlation. The correlation coefficient between the production budget and average rating was only 0.226273, which suggests a weak positive relationship. Looking at the regression plot below, the data appears to be fairly spread out and no additional patterns emerge from the analysis of this plot. It can be concluded that the overall budget has little to no impact on the average rating of a movie. Hence, a high production budget will not necessarily yield what the public considers to be a high-quality movie.
    
![Regression plot of Production Budget vs. Average Rating](images/pva.png "Regression plot of Production Budget vs. Average Rating")
    
A natural follow-up question to this would be, "Does the production budget affect the overall popularity, whether positive or negative, of the movie." To answer this question, an analysis of the production budget versus the total number of votes will be conducted. The correlation coefficient between these two values is 0.549558, which implies a moderate positive relationship between the production budget and a number of votes. Looking at the regression plot below shows a much tighter data set than the previous plot. There do appear to be multiple outliers which likely represent low-budget cult classics. These data points were left in the analysis as they represent real variations in the data. Overall, it appears that a higher production budget has a slightly positive impact on the overall popularity of the movie. 
    
![Regression plot of Production Budget vs. Number of Votes](images/pvn.png "Regression plot of Production Budget vs. Number of Votes")
    
The final question to ask from the merged data set is, "Does movie runtime have any affect on the world-wide gross?" The correlation coefficient between these two is 0.329017, which indicates a weak positive relationship. Looking at the regression plot below, it appears that the data is spread out in a similar matter to the plot of the production budget and average rating. No patterns appear to emerge from this plot. Therefore, it does not appear that the run-time has little to no impact on the overall gross of the movie.
    
![Regression plot of Production Budget vs. Runtime](images/pvr.png "Regression plot of Production Budget vs. Runtime")
    
Moving on to the Numbers dataset, the questions that come to mind are, "Does production cost affect domestic and world-wide gross? Looking at the correlation between production budget and domestic/world-wide gross, 0.685682 and 0.748306 respectively, it is apparent that there is a strong linear relationship between productiion budget and both domestic and world-wide gross. The figures below reinforce this as the data appears to be much more condensed when compared to the previous data sets. Overall, a higher budget film will generally yield a higher gross in both domestic and world-wide markets. However, this brings up a limitation of the data. The data sets do not contain information about distribution and advertising costs; therefore, profits cannot be compared to any of the metrics. Knowing the profits as well as specific distribution costs would help reinforce the current data as well as help to make informed decisions on whether or not to limit distribution to a domestic market or expand into the global market. Higher gross does generally yield higher profits so it is still reasonable to recommend higher budget movies in a domestic market. There is not enough data at this time to recommend expanding into a world-wide market as it is unclear whether the increase in gross and increase in distribution costs is enough to yield higher profits.
    
![Regression plot of Production Budget vs. Domestic Gross](images/pvd.png "Regression plot of Production Budget vs. Domestic Gross")
![Regression plot of Production Budget vs. World-Wide Gross](images/pvw.png "Regression plot of Production Budget vs. World-Wide Gross")
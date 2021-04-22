# Kickstarting with Excel
## Overview of Project
### Purpose
The purpose of this analysis is to evaluate different campaign kickstarters to analyze the relationship between their outcome of success and two important factors, launch data and goal amount.  I  specifically looked into the theather category,  in hopes to help Louise understand outcomes based on launch data and fundraising. goal amount.  The first factor I analyzed is how campaingns fared in relation to their launch date. Within this factor, I looked at which campaigns were successful,  whichs ones failed, or which ones were cancled, based on what month they were launched in. The second factor I analyzed is outcome based on fundraising goals.  Here, I looked at the percentage of success, failure, or canceled outcome based a specifical goal range. 

## Analysis and Challenges
To begin, I looked at a data sheet of multilple kickstarters and details on their goal amount, pledged amount, the outcome of the campaign, dates for deadline and launch, and category and subcategory.  The dates were orginally provivded in Unix timestamp format, but I was able to convert the value using the following code:<br />
(((A1/60)/60)/24) + DATE(1970,1,1)<br />
A1 refers to the cell with unix timestamp value. <br />
I also used the text to columns feature in excel to seperate the values in the "category and subcategory" column into two different colomuns.   This way, can analyze the data by category and subcategory individually.  <br />
I used the YEAR() function to extract the year from the converted unix time stamp, so we can evaluate outcomes based on specific years.
### Analysis of Outcomes Based on Launch Date
In this analysis, I created a pivot table from the kickstarter data to focus on the count of successfil, failed, and canceled campaigns.  I filters the pivot table by year and category.  I applied "theater" within the category filter since we are looking at theater campaigns.  From the pivot table, I ceated a chart that evaluates the count of outcomes based on months.  The dates in the analysis range frrom years 2009 to 2017, but my chart focuses on outcomes by month.  This means that within each month, it is pulling in data from that year range.
![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/63257696/115794777-98e06300-a39c-11eb-973b-6326161df3bf.png)
The most amount of successful campaigns for the theater from 2009 to 2017 were launched in May.  The number of canceled theater campaings stayed relatively low throughout every month.  In October, we can see the variance between the number of successful and failed campaigns is smaller, suggesting that the end of the year may not be a good time to launch a campaign.  We can also filter the table by year to see the trends within a sepcific year.  We see the first failed campaign data point starting in 2014, showing that there were only successes within our data range from 2009-to 2013.  




In Dec 2014, we see the number of failed campaigns reach over the number or succesfful campaigns. There seems to be trend that the number of camoaigns are not as successful towards toeend of the year, so we have tothink why.  This could be a result of the Holidays.  Typically people spend more money during the holidays, so they may have less to help a kickstarter.  However, this conclusion would depends on the country the kickstart is in because different country's will have different cultures and norms.  We wouldhave to evaluate deeper into that.  Years can  give us different conclusion because the economy is different every year
### Analysis on Outcomes Based on Goals
in this analysis we looked on the outcome of a campaign because on their goal amount.  But here, we spefically looked into the subcategory plays, which is within the theater category.  The data we extracts was the total number of successes, failures, and canceled campaings within a certain monetary value range.  I was able to use COUNTIFS function to extract this data based on the specifications.  An example of the code is below:
=COUNTIFS('Kickstarter Data'!$D:$D,"<49999",  'Kickstarter Data'!$D:$D,">=45000",'Kickstarter Data'!$F:$F, "Failed",'Kickstarter Data'!$R:$R, "plays")
we then took the count for each category and calculated the percentages of the outcomes.  We can see that lower goal amounts had higher successful campaings.  We start to see a rise in failed campigns at around $15000-$19999 range.  However, we see a spike in successful campaings again around $35000 - $40000.
### Challenges and Difficulties Encountered
launch date - only failed campaigns starting in 2014 - so number of successes in first 5 years of data might be pulling the successful numbers up as opposed to failed 
we looked at data throughout 2009 -2017. and summed the total number which told us what month had the. highest numbre of successes.  May was historically the highest, but as a total, it might different depending onoutside factors, like the economy. 
for the outcomes based on goal amounts - if you look at the actual data set, the data has higher numbers towards the lower range goals.  The higher range goals have less amount of campaings, therefore having a ratio that fluctates more if another data point is added.
because the grpah is show in percerntages, a spikee in successful might not actually mean the campaings will be in successful
## Results 
need 2 on launch data
need. 1 on gioal
I think that when looking at the charts, it clearly shows that a good timee to launch a campaign would be in May, to avoid the later months in the eyar, and to start with a ressonable and low goal range.  However, I think we should question the results of the data.  Fpr example, the higher range goal amount had 2:1 success- we should question what made that success.  We should not rely on the two data point alone into generating factors for a campaign.  

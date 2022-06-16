# An Analysis of Kickstarter Campaigns
Performing analysis on Kickstarter data to uncover trends

## Overview:
This challenge was to compare how fund-raising campaigns for plays faired. Using data from kickstarter campaigns, I visualized campaign outcomes based on their launch dates and their funding goals.

## Purpose:
This challenge demonstrates my ability to comb through data using sorting and filtering tools, summarize and process it using functions and pivot tables, then demonstrate the results using graphics.

## Analysis and Challenges:

### Analysis of Outcomes Based on Launch Date

First, I needed to create a row lableled years. To do this, I utilized the YEARS() function in order to pull the year portion out of the date created function as such:

``=YEAR(T2)``

Next, I needed to create a pivot table utilizing all of the data that would summarize theater outcomes of completed campaigns sorted by year. To do this, I selected Insert, then Pivot Table, selected the whole data set, and created my table in its own sheet. I renamed this sheet "Theater Outcomes by Launch Date." I set the filters for this table to be "Parent Category" and "Years." I set the columns to "Outcomes" and removed the "live" result from the column lables. I set the Rows to be the "Date Created Conversion" such that it would display the results by month. Finally, the values were set to the "Count of Outcomes." I then filtered my data such that the parent category was "theater" and sorted my data by the descending outcomes. This table therefore displays the results of completed theater Kickstarters by month. This table is filterable by the year the Kickstarter was created. The table also displays the data by showing successful campaigns first.

To finish off this analysis of theater campaigns, I created a line chart to display these results and labeled it "Theater Outcomes Based on Launch Date."

### Analysis of Outcomes Based on Goals

Next I was to create a summary of the outcomes based on ranges of goals.

To do this, I created a new sheet and renamed it "Outcomes Based on Goals." I then created the column labels: "Goal," "Number Successful," "Number Failed," "Number Canceled," "Total Projects," "Percentage Successful," "Percentage Failed," and "Percentage Canceled."

Next, I needed to be able to sort and demonstrate my data by a variety of ranges of goals. So, I filled out the "Goal" column with these ranges.

To fill the "Number Successul" column, I used COUNTIFS() to filter data from the Kickstarter sheer for my chosen range of goals, for if the campaign was successful, and for if the campaign was a play as such:

`=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<4999",Kickstarter!$F:$F, "=successful",Kickstarter!$R:$R,"=plays")`

Similarly, I used COUNTIFS() to fill out the "Number Failed" and "Number Canceled" sections as well:

`=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<4999",Kickstarter!$F:$F, "=failed",Kickstarter!$R:$R,"=plays")`
`=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<4999",Kickstarter!$F:$F, "=canceled",Kickstarter!$R:$R,"=plays")`

Next, I filled the "Total Projects" column utilizing the SUM() function across the "Number Successful," "Number Failed," and "Number Canceled" columns as such:

`=SUM(B2:D2)`

To fill out the "Percentage Successful," "Percentage Failed," and "Percentage Canceled" columns, I set their data types to percentages then divided the respective "Number" column by the "Total Projects" as such:

Percentage Successful
`=B2/E2`
Percentage Failed
`=C2/E2`
Percentage Canceled
`=D2/E2`

To better visualize the results of this analysis, I created a table utilizing the percentages as the y-axis and the ranges of goals as the x-axis. This chart demonstrated the resulting percentages of each outcome based on the range of goals they fall into.

## Challenges and Difficulties Encountered

The primary difficulty I had encountered was setting up my pivot table for the Outcomes Based on Launch Date. I found it particularly difficult to find out what categories to set up as columns, rows, or values to display the variety of outcomes by month. After testing around, I discovered that I could set the the dates to the rows to display the months. Additionally, I discovered that I could utilize the outcomes for both the columns and the values sections.

The other difficulty I encountered while working on these projects was when I would maneuver through different sheets while inputting values for functions. During this time, excel would automatically input the sheet I moved to as a value in my function. As such, if I was moving around to simply look at data, I would have to use caution that extra values were not being inputted into my formulas.

## Results

What are two conclusions you can draw about the Outcomes based on Launch Date?

![Theater Outcomes Based on Launch Date](https://github.com/waciciarelli/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png?raw=true)

1. Based on the results of Outcomes Based on Launch Date, it is demonstrated that very few campaigns were not seen through to completion. For those that had completed their Kickstarter campaign, more were successful than failed for each month. 
2. While both the successful and failed campaigns increase as the total number of campaigns increases, there is a notable spike in May for the number of successful campaigns compared to only a small increase for the number of failed campaigns. This would suggest that May would be the optimal time to start a campaign for a theater.

What can you conclude about the Outcomes based on Goals?

![Outcomes Based on Goals](https://github.com/waciciarelli/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png?raw=true)

Based on the results of the Outcomes Based on Goals, it is shown that kickstarters for plays are generally more successful when their goals are lower than 15000. This is denoted on the chart above where the percentage successful first meets the percentage failed. However, there are also notable spikes later on in the graph. starting before 35000 and continuing after 40000, the percentage of successful campaigns is greater than the percentage of failed campaigns.

What are some limitations of this dataset?

The primary limitation of this dataset is that it is perhaps too broad. This dataset may perform more accurately if it were filtered by country. This would provide a much more applicable result as well, as one would be able to more accurately predict the result of thier kickstarter within their own country rather than within the world overall.

What are some other possible tables and/or graphs that we could create?

Other tables and graphs that could be created include, but are not limited to:

Percentage of kickstarters that were seen to completion.
Comparing the percentage of successes and faiures based on parent category or subcategory.
Comparing the number of campaigns within a particular category or subcategory based on country.
Comparing the average amount pledged for each category in a bar graph filterable by country.

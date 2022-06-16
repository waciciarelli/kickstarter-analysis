# An Analysis of Kickstarter Campaigns
Performing analysis on Kickstarter data to uncover trends

Overview:
This challenge was to compare how fund-raising campaigns for plays faired. Using data from kickstarter campaigns, I visualized campaign outcomes based on their launch dates and their funding goals.

Purpose:
This challenge demonstrates my ability to comb through data using sorting and filtering tools, summarize and process it using functions and pivot tables, then demonstrate the results using graphics.

Analysis and Challenges:
First, I needed to create a row lableled years. To do this, I utilized the YEARS() function in order to pull the year portion out of the date created function as such:
``=YEAR(T2)``
Next, I needed to create a pivot table utilizing all of the data that would summarize theater outcomes of completed campaigns sorted by year. To do this, I selected Insert, then Pivot Table, selected the whole data set, and created my table in its own sheet. I renamed this sheet "Theater Outcomes by Launch Date." I set the filters for this table to be "Parent Category" and "Years." I set the columns to "Outcomes" and removed the "live" result from the column lables. I set the Rows to be the "Date Created Conversion" such that it would display the results by month. Finally, the values were set to the "Count of Outcomes." I then filtered my data such that the parent category was "theater" and sorted my data by the descending outcomes. This table therefore displays the results of completed theater Kickstarters by month. This table is filterable by the year the Kickstarter was created. The table also displays the data by showing successful campaigns first.
To finish off this analysis of theater campaigns, I created a line chart to display these results and labeled it "Theater Outcomes Based on Launch Date." Below is a look at this chart
![Theater Outcomes Based on Launch Date](https://github.com/waciciarelli/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png?raw=true)

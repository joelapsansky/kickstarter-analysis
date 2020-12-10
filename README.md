# Kickstarting with Excel
## Overview of Project
Louise would like to find out how certain campaigns performed relative to their fundraising goals and launch dates.
### Purpose
Our analysis will uncover insights for Louise through visualizations that display success rates by dates and bucketed goals.  The scope is the entire Theater category, but for specific goals, the scope is just the Play subcategory.
## Analysis and Challenges
Louise can look at successes, failures, and canceled Theater campaigns, but this only tells some of the story.  It is also good to see success rates for different goals (i.e. small goals, big goals, and everything in between) in the deeper subcategory.  Line charts are a good way to display the information.  When conducting the analysis, I initially forgot that you needed to put quotes within the COUNTIF statements in order to set the ranges.  For example, “greater than $1,000” is “<=”&1000, and not <=1000.  The function does not work without the proper syntax.
### Analysis of Outcomes Based on Launch Date
![Theater Outcomes vs Launch](/Theater_Outcomes_vs_Launch.png "Theater Outcomes vs Launch")
In total, it is clear that successes far outnumber failures for Plays.  Successes outweigh failures for each month as well.  In fact, the data shows that over half of each month's Theater/Play campaigns were successful, and this rate of success is very steady.  December has the lowest success rate at 49% whereas May has the highest success rate at 67%.  I found this by dividing the successful column of the pivot table by the Grand Total column for each row in the column.  May also saw the highest number of campaigns; December saw the lowest number of campaigns.  Number of campaigns seems to impact success rate.  
### Analysis of Outcomes Based on Goals
![Outcomes vs Goals](/Outcomes_vs_Goals.png "Outcomes vs Goals")
After setting the goal bucket and creating the table columns, I used the COUNTIF function to calculate the number of successful, failed, and canceled plays within each range.  As an example, here is the code snip for number of successful Plays in range $10,000 to $14,999:
=COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$D:$D,">="&10000,Kickstarter!$D:$D,"<="&14999,Kickstarter!$R:$R,"plays").
This code refers to the Kickstarter tab, which houses the full dataset.
Most Play campaigns have goals less than $10,000.  In these three ranges, most projects are successful so it’s possible that these were realistic goals that were achieved, or that the bar was set too low.  It’s clear that the success rates drop for goals in the $15,000 to $34,999 range.  Perhaps these goals were erroneously set too high due to higher expectations.  It is also possible that there was more uncertainty around what success should look like for these campaigns.  Of course, there are other potential explanations.  With the exception of the highest goal bucket ($50,000+), campaigns that had goals in the $35,000 to $49,000 range did really well.  There is a lot of intersection in the chart.  It seems that the fluctuation is due to expectations when goal setting, but there are many other effects that could have contributed to campaigns failing (e.g. demographics and average pay of donors in specific campaign locations).  Unfortunately, that information is not in the dataset.
### Challenges and Difficulties Encountered
When conducting the analysis, I initially forgot that you needed to put quotes within the COUNTIF statements in order to set the ranges.  “Greater than $1,000” is “<=”&1000, and not <=1000, but everything calculated after the change.
Additionally, it is worth noting that in this dataset, the possible outcomes are already defined for us in their own column so this “success bar” was already set before starting the analysis.  
## Results
Theater as a whole fared really well just about every month, but especially in May where we see the greatest spike.  December had the lowest success rate at 49% as compared to May’s 67% success rate.  It would have been nice to see location and weather to better determine seasonality.  Means of fundraising would have added color as well.
As mentioned above, most Play campaigns had goals less than $10,000, and for those goals, most of the projects were successful.  Success rates drop for goals in the $15,000 to $34,999 range.  It would have been good to see the locations of these campaigns to analyze their effects.  Demographics of donors would have been helpful too.  These are definitely some limitations.  
We could have created a histogram chart to heighten the analysis.  If we had some additional info, we could have run regressions too.  
Lastly, as a key takeaway, it is important to note that while the Theater category saw great success, there were certain campaigns in the Play subcategory that did not fare well.  When we have multiple ways to slice the data, it is important to drill down to paint the full picture.



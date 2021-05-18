# An Analysis of Kickstarter Campaigns
##### Performing analysis on Kickstarter data to uncover trends
---

## Overview of Project
This report will look at more than 4000 kickstarter crowdfunding campaigns from different countries. The data analyzed includes the name, blurb, funding goal, amount of money pledged, outcome, country, currency, deadline, date launched, number of backers, category, and subcategory. The goal of the analysis is to help Louise compare similar campaigns to better approach hers. We will evaluate how the funding goal and different launch dates affected the outcome of theater/plays campaigns. 

## Challenges
To begin our analysis we needed to filter the data to analyze campaigns similar to Louise's play she needed to fund. However, the category and subcategory were together in the same column. Here we faced our first challenge. If we wanted to filter the data even more to come up with a better analysis, we needed to separate the category and subcategory in two different columns. We did this by using the *text to column* option in excel, separating the two strings that were joint by a "/" into two differnt columns.

Moreover, the second challenge we faced was that the deadline and the date launched were in a *Unix Timestamp* unit. We converted it to a normal date by using the function `=(((J2/60)/60)/24)+DATE(1970,1,1)` to divide it back to minutes, hours, and days and to bring it back to the default date of January 1st, 1970. We repeated this process for the deadline and date launched to create two new columns. Finally, we created one last column to store jusst the year of the date that the campaign was created. This way we could filter the data by years anytime we wanted. We did this by using the `=YEAR()` function in excel. 

## Analysis
### Theater Outcomes Based on Launch Date
We wanted to begin our analysis by looking at theater campaign outcomes based on their launch date. We did this by creating a Pivot table with *Category* and *Years* as filters, *Outcome* as column, *Date created* (being shown as months) in rows, and *count of Outcomes* as values. We filtered the theater category campaigns so that we narrowed the analysis to just the ones similar to Louise's campaing to end up with **Exhibit 1:**

![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/83378141/118408742-d3b08080-b654-11eb-99d6-5b295973f394.png)

Here we can observe a count of how many theater campaigns were created in each month and how many of them were successful, canceled, or failed. 

### Plays Outcomes Based on Goals
Furthermore, we wanted to analyze the outcomes of theater/play campaigns based on their funding goals. We were able to do this by filtering the campaings by the subcategory *plays*, outcomes (*successful, failed, and canceled*), and grouping the campaings in the following goal intervals: 
- Less than 1,000
- 1,000 to 4,999
- 5,000 to 9,999
- 10,000 to 14,999
- 15,000 to 19,999
- 20,000 to 24,999
- 25,000 to 29,999
- 30,000 to 34,999
- 35,000 to 39,999
- 40,000 to 44,999
- 45,00 to 49,999
- Greater than 50,000

![Exhibit2](https://user-images.githubusercontent.com/83378141/118409235-5e927a80-b657-11eb-9872-e012974b1ca5.png)

We were able to do this by using the `=COUNTIFS` function with multiple 'if' conditions depending on their interval and outcome. For example, to count how many successful play campaigns there were that asked in between $1,000 and $4,999 dollars, we used `=COUNTIFS(Kickstarter!D:D,">=1000",Kickstarter!D:D,"<=4999",Kickstarter!F:F,"successful",Kickstarter!R:R,"plays")`, to see there were 388 campaings with this characteristics. Then, we calculated the total projects for each interval (row), to come up with the percentages of each outcome that will allow us to interpret the data better. The percentages can be interpreted as the amount of successful campaigns out of the total with that same funding goal interval. For our continious example, those 388 successful campaignes would be the 72.66% of all the campaigns that asked for $1,000 to $4,999 dollars. The rest 27.34% acounted for the failed campaings, as there were no canceled ones. 

![Outcomes_vs_Goals](https://user-images.githubusercontent.com/83378141/118409743-f1ccaf80-b659-11eb-97a9-aa14e5232c0d.png)

Here we can see the percentage of successful and failed campaigns throughout different funding goal intervals from less than $1,000 to more than $50,000. 

![Outcomes(count)_vs_Goals](https://user-images.githubusercontent.com/83378141/118409744-f5f8cd00-b659-11eb-801a-e8a1afa732b2.png)

**Extra Exhibit**. And here we can see the count of successful and failed play campaigns in different intervals as well. 

## Results
After conducting the analysis from the *outcomes vs launch date* portion, we were able to infer that there were relatively more successful campaigns launches during May-June. Meanwhile, at the end of the year (October to December) the successful campaigns happened to decline. So, a good recommendation for Louise could have been to launch her campaign in May as data shows they are more likely to succeed during this time. On the other hand, failed campaigns don't seem to show a strong pattern. They just range between the 30 to 50 count with a few spikes and downfalls. 

From the *outcomes vs goals* portion, we were able to conclude that the percentage of successful campaings was higher than failed in the goal intervals *less than $1,000 to $15,000*. This percentage distribution **was higher for successful in smaller funding goals**, as we can see in the interval *less than $1,000 and $1,000 to $4,999*. From this point, the failed campaigns represented a higher percentage from $15,000 to $35,000. 

More specifically, we then came up with one last line graph **(Exhibit 3: Outcomes (count) based on Goals)**, which showed that the amount of successful campaigns was considerable higher in the *$1,000 to $4,999* interval. Allowing us to conclude that Louise should consider for sure coming up with a campaign goal within the range of $0 to no more than $15,000, but more specifically, it should be in the range of $1,000 to $4,999 as data shows this happens to be the sweet spot where campaigns have succeeded the most. 

### Dataset Limitations
Moreover, the dataset limitation we encountered was that the data was a bit too old. If we wanted to suggest Louis to take a certain course of action after analyzing the kickstarter data we were given, we would want to include some more data past 2017. This way, we could make a better recommendation. Out of the 4,114 campaigns we had 3,037 were from the US and 603 were from Great Britain. If we woulnd have wanted to help Louis come up with a play fundraising campaign in Great Britain we would have appreciated a larger dataset. Other than that, the data was clean and straight forward. It had all of the information we could have wanted for kickstarter campaigns.










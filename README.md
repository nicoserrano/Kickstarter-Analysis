# An Analysis of Kickstarter Campaigns
##### Performing analysis on Kickstarter data to uncover trends
---

## Overview of Project
This report will look at more than 4000 kickstarter crowdfunding campaigns from different countries. The data analyzed includes the name, blurb, funding goal, amount of money pledged, outcome, country, currency, deadline, date launched, number of backers, category, and subcategory. The goal of the analysis is to help Louise compare similar campaigns to better approach hers. We will evaluate how the funding goal and different launch dates affected the outcome of theater/plays campaigns. 

## Challenges
To begin our analysis we needed to filter the data to analyze campaigns similar to Louise's play she needed to fund. However, the category and subcategory were together in the same column. Here we faced our first challenge. If we wanted to filter the data even more to come up with a better analysis, we needed to separate the category and subcategory in two different columns. We did this by using the *text to column* option in excel, separating the two strings that were joint by a "/" into two differnt columns.

Moreover, the second challenge we faced was that the deadline and the date launched were in a *Unix Timestamp* unit. We converted it to a normal date by using the function `=(((J2/60)/60)/24)+DATE(1970,1,1)` to divide it back to minutes, hours, and days and to bring it back to the default date of January 1st, 1970. We repeated this process for the deadline and date launched to create two new columns. Finally, we created one last column to store jusst the year of the date that the campaign was created. This way we could filter the data by years anytime we wanted. We did this by using the `=YEAR()` function in excel. 

## Analysis
We wanted to begin our analysis by looking at theater campaign outcomes based on their launch date. We did this by creating a Pivot table with *Category* and *Years* as filters, *Outcome* as column, *Date created* (being shown as months) in rows, and *count of Outcomes* as values. We filtered the campaigns for us just to see the theater category to end up with **Exhibit 1**. 

[Exhibit1](Exhibit1.png)





# An Analysis of Kickstarter Campaigns
##### Performing analysis on Kickstarter data to uncover trends
---

## Overview of Project
This report will look at more than 4000 kickstarter crowdfunding campaigns from different countries. The data analyzed includes the name, blurb, funding goal, amount of money pledged, outcome, country, currency, deadline, date launched, number of backers, category, and subcategory. The goal of the analysis is to help Louise compare similar campaigns to better approach hers. We will evaluate how the funding goal and different launch dates affected the outcome of theater/plays campaigns. 

## Analysis and Challenges
To begin our analysis we needed to filter the data to analyze campaigns similar to Louise's play she needed to fund. However, the category and subcategory were together in the same column. Here we faced our first challenge. If we wanted to filter the data even more to come up with a better analysis, we needed to separate the category and subcategory in two different columns. We did this by using the *text to column* option in excel, separating the two strings that were joint by a "/". 

Moreover, the second challenge we faced was that the deadline and the date launched were in a *Unix Timestamp* unit. We converted it to a normal date by using the function '''=(((J2/60)/60)/24)+DATE(1970,1,1)''' to bring it back to the default date of January 1st, 1970. 

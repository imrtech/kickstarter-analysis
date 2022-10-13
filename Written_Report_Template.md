# Kickstarting with Excel

## Overview of Project

### Purpose

The purpose of this analysis was to observe how different campaigns performed in relation to the dates they launched and their funding goals. We used the Kickstarter data file for our analysis.


## Analysis and Challenges

The Kickstarter data is comprised of several worksheets. The first worksheet I analyzed was the Kickstarter worksheet which contained 4114 records. 

Step 1: Filter the data by dates
    Since I needed to filter the data by dates I used empty column U to create a new column header named "Year".  I used the following formula:

    `Year()`

To use this formula, I selected the first cell (underneath my newly created column, cell U2). I entered the formula >Year(), then placed my cursor between the parentheses. This called up the data that would be used in my formula. In this case it called up "serial_number". I selected the data from cell S2 (column S and Row 2) for the column header Date Created Conversion. It added the cell's data within the parentheses. I pressed enter to run the formula and it extracted the year and added it cell U2. I then applied the formula to the rest of the cells in column U (Years). 

I then created a new pivot table that filtered for the Theater parent category and Years. I then added outcomes to values area as well as the columns area, and finally I added the Months (Date Created Converstion) to the rows area. From this result, I charted a line graph and entitled it Theater Outcomes Based on Launch Date. I saved this image here:

I created a new worksheet for Theater Outcomes Based on Launch Date. This included 8 new columns and 9 rows.
![This is an image](/Theater_Outcomes_vs_Launch.png)

I created a new worksheet for Outcomes Based on Goal.
![This is an image](https://github.com/imrtech/kickstarter-analysis/blob/5af195e67d7a248d09e8de1a22067418ce6538e2/Outcomes_vs_Goals.png)


### Analysis of Outcomes Based on Launch Date

May and June were the most successful launch months for the theater campaign. However, roughly 36% of the theater campaigns failed to meets its goals.

### Analysis of Outcomes Based on Goals

Of the 1047 Plays Campaigns, 694 were successful. 529 Campaigns with goals less than $1,000 and between $1,000 and $4,999 were the most successful. 

As the goals amount increased the less campsigns were launched.

### Challenges and Difficulties Encountered


## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?

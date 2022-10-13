# Kickstarting with Excel

## Overview of Project

### Purpose

The Fever Play campaign did not reach it's intended funding goal. We will use the Kickstarter data to analysis and make observations on how different campaigns performed in relation to the dates they launched and their funding goals. We will specifically look at the Parent Category Theater and SubCategory Plays which the Fever Play campaign was grouped under in the dataset.


## Analysis and Challenges

The Kickstarter data file is comprised of several worksheets in excel. The first worksheet I analyzed was the Kickstarter worksheet which contained 4114 records. 
Since this is a large data set, we want to go ahead and make the data easier to read and filter as much as possible. Here is a link to the data file: [filename](/Kickstarter_Challenge.zip)

### Analysis of Outcomes Based on Launch Date

To visualize the dates the campaigns launched by Year, I created a new column U and added a new header named "Year".  
-  I used the following formula:

    `Year()`

- To use this formula, I selected the first cell (underneath my newly created column, cell U2). I entered the formula `Year()`, then placed my cursor between the parentheses. This called up the data that would be used in my formula. In this case it called up "serial_number". I selected the data from cell S2 (column S and Row 2) for the column header Date Created Conversion. It added the cell's data within the parentheses. I pressed enter to run the formula and it extracted the year and added it cell U2. I then applied the formula to the rest of the cells in column U (Years). 

-  I want to easily visualize the relationship between successful, failed and canceled campaigns under the Parent Category Theater. In order to see this I created a pivot table. 
    -  While in the Kickstarter worksheet, I selected the Insert tab from the Excel Navigation menu and clicked on Pivot Table. 
    -  I named the worksheet "Theater Outcomes by Launch Date."
    -  I added the fields Theater parent category and Years in the filters area. I then added the outcomes field to the values and columns area. Lastly, I added the Months (Date Created Converstion) to the rows area. This would give me the monthly trends.
    -  From this result, I charted a line graph and titled it "Theater Outcomes Based on Launch Date". 
    -  Below is an image of the line chart:

    -  ![This is an image](/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals

Now I want to further breakdown the data and look at how the subcategory Plays performed based on Goal amounts. This is expecially helpful for our analysis since the play "Fever" belongs in this subcategory.

I created a new worksheet and named it Outcomes Based on Goal. This included 8 new columns and 12 rows.
-  The first column (Column A) named Goal, contained a range of amounts. The remaining columns B through H, were named Number of Successful, Number Failed, Number Canceled, Total Projects, Percentage Successful, Percentage Failed, and Percentage Canceled.
-  Columns B, C, and D, would require the `COUNTIFS` formula to filter out the Number of Successful, Failed and Canceled campaigns in the range amount and for subcategory "Plays". 
-  Here is what the formula for cell B2 would look like: `=COUNTIFS(Kickstarter!$F:$F, "successful",Kickstarter!$D:$D,"<1000",Kickstarter!$R:$R,"plays")`
    -  What this formula does is it will give you the count of all records found in the Kickstarter worksheet that have the following criteria: had successful outcomes; in the range of Less than 1000; and in subcategory plays.
    -  I then copied this formula to the remaining cells B3 through B13, paying close attention that the only parameters that would need to change for those cells is the goal range. For example, cell B3 would look like this: `=COUNTIFS(Kickstarter!$F:$F, "successful",Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999",Kickstarter!$R:$R,"plays")`. This means give me the count of all records found in the Kickstarter worksheet that had successful outcomes; between 1000 and 4999; and in subcategory plays.
    -  I used the same method for Columns C and D only changing the outcomes status from successful to failed and canceled. For example in cell C2 for number of failed plays less than 1000 the formula I used was: `=COUNTIFS(Kickstarter!$F:$F, "failed",Kickstarter!$D:$D,"<1000",Kickstarter!$R:$R,"plays")`
-  For column Total Projects, I took the sum of all outcomes based on the range amount. Here is the formula I used in cell E2: `=SUM(B2:D2)`. I then applied the formula to the rest of the cells in the column. 
-  For column Percentage Successful, I divided the Number of Successful outcomes by the Total projects for each goal range. This is the formula I used for cell F2: `=B2/E2`. I then changed the data type to percentage and remove the decimal points. I applied this formula to the remaining cells in the column.
-  For columns Percentage Failed and Percentage Canceled, I used the same method as the Percentage Successful, only this time I would change the referenced cells to reflect the Number Failed and Number Cancelled at each goal range. For example, for cell G2 to get the Percentage Failed, I divided cell C2 (Number Failed for Less than 1000) by E2 Total Projects. Formula used is: `=C2/E2`
-  From this result, I selected the columns Goal, Percentage Successful, Percentage Failed, and Percentage Canceled and clicked on the Insert tab in excel and selected a line chart and titled it "Outcomes Based on Goals". 
    -  Below is an image of the line chart:

    -  ![This is an image](/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered

I had to be careful with some of the formulas. In the `COUNTIFS` formula used in the Outcomes Based on Goal worksheet, I had to make sure that the Kickstarter worksheet and specific columns referenced, did not change when I applied the formula to the remaining fields in the Outcomes Based on Goal. For example, I had to make sure that I properly referenced the the kickstarter worksheet and that I used a $ in front F column range such as `$F:$F`

In addition, I had to make sure I was using the correct character for less than, between and greater than in the `COUNTIFS` formula. An incorrect character would have produced an invalid or wrong result.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
  
  May and June were the most successful launch months for the theater campaign. After the month of June there was a steady decline in successful campaigns for the remainder of the year. Overall, 61% of the theater campaigns were successful, while roughly 36% of the theater campaigns in general failed to meets its goals and 3% were canceled.

- What can you conclude about the Outcomes based on Goals?
  
  Of the 1047 campaigns for plays, 66% or 694 were successful. The most succcessful campaigns represented smaller goal amounts. 529 Campaigns with goals less than $1,000 and between $1,000 and $4,999 were the most successful. As the goal amounts increased less campaigns were launched. There is an uptick in successful outcomes in the goal amounts ranging from $35,000 to $44,999. But it is unclear why. 

  The plays also had a higher successful outcome in the months of May and June. This would be consistent with the success during the same months for the parent category Theater.

- What are some limitations of this dataset?
  
  A limitation is that we don't see any information about the markets or cities in each country. Campaigns in one market or city might be more successful than another. If so, I'd like to see that and if there are trends throughout the same months in the year.

  Some campaigns had a different duration. This could impact the success of a campaign. 

- What are some other possible tables and/or graphs that we could create?
  
  A line graph of campaign performance for plays in different countries would be helpful. 
  
  A pivot table filtering for succcessful, failed and canceled campaigns for subcategory Plays through the months of the year.
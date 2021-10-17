# Kickstarting with Excel

## Overview of Project

### Purpose
Louise is a playwright who was looking at using Kickstarter to crowdsource the funds for her first play, "Fever". She was hoping to get insight into how successful her campaign will be, so I used the Kickstarter data provided to help the success of her Kickstarter campaign. Since her campaign has already launched, she wants to know how Kickstarter campaigns fared as functions of their launch dates and their funding goals. The purpose of this project is to present Louise with helpful and accessible data from other Kickstarter campaigns to help answer her questions.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
The first analysis was of Kickstarter outcomes based on their launch date. To achieve this comparison, some of the data needed to be reformatted: the launch date data needed to be converted from Unix timestamps to a readable format and the category/subcategory data needed to be split into parent category and subcategory. The date conversion was important to allow the data to be sorted by month and year. The splitting of the category wasn't strictly necessary to complete this task, but allowed the data to be more easily sorted. The analysis of the data was then accomplished via pivot table, as shown in Figure 1. The outcomes, either successful, failed, or canceled, were tabulated as a function of the month they were started in. The data was further filtered by the Parent Category of Theater.  This data was turned into a chart via PivotChart to allow ease of accessibility, which can be seen in Figure 2. 


![Theater_Outcomes_vs_Launch_Pivot.png](/Resources/Theater_Outcomes_vs_Launch_Pivot.png)

Figure 1. Table of theater Kickstarter campaign outcomes as a function of launch date.


![Theater_Outcomes_vs_Launch.png](/Resources/Theater_Outcomes_vs_Launch.png)

Figure 2. Theater Kickstarter campaign outcomes plotted as a function of launch date.

### Analysis of Outcomes Based on Goals
The second analysis was of the Kickstarter outcomes based on their goals. The splitting of the category/subcategory data that had already been completed helped this analysis as well, but similarly was not absolutely necessary. Ranges were chosen for the goals which would allow the data to be more easily understood. The final result was the percentage of each play outcome as a function of the goal ranges. The goal ranges and the percentages can be seen on the data table shown in Figure 3. These values were displayed in a line plot, as shown in Figure 4.


![Outcomes_vs_Goals_Table.png](/Resources/Outcomes_vs_Goals_Table.png)

Figure 3. Table of calculations for play Kickstarter outcomes as a function of the campaign's goal.


![Outcomes_vs_Goals.png](/Resources/Outcomes_vs_Goals.png)

Figure 4. Play Kickstarter outcomes plotted as a function of the campaign's goal.

### Challenges and Difficulties Encountered with Outcomes Based on Launch Date
For the first analysis, converting the launch date could have been a significant challenge if the analyst didn't know that it was a Unix timestamp, and how to convert it accordingly, as trying to change the cell formatting to date doesn't work for Unix timestamps. The Unix timestamp was converted by dividing the timestamp, which is seconds since January 1st, 1970, to turn the number into days since 1/1/1970, and adding it to the date 1/1/1970. Splitting the category column could have been a challenge for the analyst as the text is not easily split into two cells by a line of code in Excel. This was achieved by utilizing the Text to Column Wizard and delimited by backslashes. Pivot tables can be tricky as it can be easy to choose a field for the filters, rows, columns, or values that may not present the data you want. This choice can also make the resulting PivotChart confusing. Choosing the correct graph type can similarly be a challenge, but line graphs are the clearest way to track the progression of multiple datasets over time. 

### Challenges and Difficulties Encountered with Outcomes Based on Goals
The second analysis was substantially more challenging. To obtain the percentage of each, a count of all successful, failed, and canceled play Kickstarter had to be obtained for each goal range. Live play outcomes were ignored as they would not add any substance to this analysis. A combination of filtering, sorting, and the COUNTIF() function were used to determine the number of each outcome per range of just the plays. First all the Kickstarter campaigns were sorted by goal value from smallest to largest, then the subcategories were filtered to be just plays, and finally a COUNTIF() function was used to check the outcome of each Kickstarter. The order here is important, as it results in all the play campaigns in order of goal with no rows in between. When selecting data for the COUNTIF() function, if there are rows that are hidden in the data set, the data in those rows are still included in the COUNTIF() range. By filtering/sorting in the order described, when the last filter of the goal amount was applied, there were no hidden rows in the selected data. Solving this challenge proved difficult as I could not find an easy way to only select the visible rows or checking that any one outcome cell in the data range selected was in a row that had both a play as the subcategory and a goal in the relevant range. Creating this table would have been difficult if I had been trying to use a pivot table because the goal values would not have been grouped into the ranges as desired.

## Results

### Conclusions from Outcomes Based on Launch Date
The two main conclusions drawn from this data are that there are more successful theater Kickstarter campaigns launched in May than in any other month and that in December there are almost as many failed theater Kickstarter campaigns as successful theater Kickstarter campaigns.

### Conclusions from Outcomes Based on Goals
From the play Kickstarter outcomes based on their goals, the success of the Kickstarter is less likely as the goal amount increases. This conclusion is dependent on the exception of data with goal amounts between 35000 and 50000 as there are not enough data points to form an accurate conclusion.

### Limitations of the Dataset
A limitation of the dataset is the quality of the Kickstarter campaigns in these two analyses are in no way measured, so the month of December may look like a bad time to launch a Kickstarter, but it may be due to the quality of theater Kickstarter campaigns in December being of a significantly lower quality than those submitted in May. Outside of quality, there are many other factors that could be contributing to the success of a Kickstarter campaign, including but not limited to: popularity of group or individual before Kickstarter launch, amount and type of promoting the Kickstarter outside of Kickstarter's generic algorithm, and originality of the content.

### Recommendations for Additional Tables/Graphs
For the first analysis, the addition of a 100% stacked column bar chart of the same data could be helpful to see which month has the highest percentage of theater Kickstarter campaigns launched that are successful. Additionally, changing the filter to be subcategory:plays instead of parent category:theater could provide more specific data to Louise. Lastly, a graph that was the number of Kickstarter campaigns as a function of the launch month with every individual year as a separate set of data could indicate if trends are have changed in recent years.

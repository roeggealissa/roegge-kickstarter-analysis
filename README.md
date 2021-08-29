# roegge-kickstarter-analysis
# Trend finding in Kickstarter data using Excel

### Introduction 

The client, Louise, has contacted us regarding a play they are planning to launch in America using the crowd funding website Kickstarter. This website has the user to specify a minimum funding goal and a project deadline by which the minimum goal must be reached; if the goal is not reached the money is returned to the investors. Louise’s project is a play titled Fever with an initial estimated budget of around 12,000 USD and no set deadline. This report details the analysis of Kickstarter data, initial conclusions drawn, and limitations of the dataset or analysis are addressed.

### Data Analysis

##### Data

The dataset provided contains information on 4115 Kickstarter projects. Included is information such as if a project was successful, what their overall goal was, when did the project start and end, and a basic description of each ‘Kickstarter’. The file was a .xlsx extension type Microsoft Excel file containing one sheet. The sheet contains a variety of data types from financial to strings.

##### Analysis

The first item addressed in the worksheet was the start and end date of the campaign. This data was delivered in Unix time stamps and thus was converted using a date conversion formula to turn the data into a readable format. In order to make the sheet more accessible for Louisa, conditional formatting was used to color code outcomes of projects so that a visual look is sufficient to see if a project was successful or not. Using the goal and pledged categories we created the new category of “percentage funded” which provides a metric to measure how close to the project goal did the Kickstarter manage to raise. This metric allows for both us and Louisa to quickly determine if there are certain projects that receive low amounts of interest versus projects that exceed their funding goal. The pledged goals and backer number allow us to measure what the average donation of each Kickstarter is which is another metric of interest.

Since Louisa specifically wants to launch a play, we separated the “Category” column into “Parent Category” and “Subcategory” to look specifically at how theater projects, and plays specifically, perform on the platform. We can now filter the sheet or pivot tables to only look for plays to allow us to complete a more relevant analysis for Louisa. 

##### Challenges 

The first challenge was the date conversion. As we don’t have access to each webpage each Kickstarter exists on, we have no way to verify that the start and end dates are accurate. There is also some extraneous information included in the sheet that may be useful to the client but not to our analysis, such as the blurb of each Kickstarter, if it was a staff pick or spotlighted at any point, and the currency used for the Kickstarter. A number of live campaigns were included, which were not included in the analysis.

As many of the campaigns received no funding, we included iferror functions into calculations such as the percentage funded or average donations to ensure the sheet did not return #DIV/0 errors. 


### Conclusions

##### Campaign Launch Date against Outcome

The client does not have a firm launch date, so using Pivot Tables and Pivot Charts we studied if there was a correlation between the date a Kickstarter is launched and the likelihood of successful funding.


![Figure 1: Month the campaign is launched in against the overall number of successes or failures.](https://github.com/roeggealissa/roegge-kickstarter-analysis/blob/a5bada078c7a4a80b96620d5bb01233834340cc6/Theater_Outcomes_vs_Launch.png)

From this graph we can draw a couple of initial conclusions. The first conclusion is that there is a correlation between launching during the mid-year months of May, June, and July and increased project success. May had the most overall successes at 111 successful Kickstarter projects. It is important to note however that overall, there are more Kickstarter projects started in those months on average, so the number of failures is also increased for those months. The average ratio of successful to failed projects throughout the data set is 1.68 projects, and this three month period has success to failure ratios for the May through July period exceeded the average.

The second conclusion that can be drawn is the months of October and December display a lower success to failure ratio. The ratio in both months falls to below the 1.68 average to 1.3 and 1.05 respectively.  This could have a variety of reasons for the correlation, such as less projects overall submitted to Kickstarter in that period, or a higher rate of failed projects compared to the average. 

The month of February is another alternative launch month. While it does not have the same high success rate of the early summer months, it does have an increase in successful projects and doesn't have the same overall submission rate of projects as the summer months.

The recommendations based on the results are as follows:

-We recommend aiming for a starting launch date between May 1st and July 31st.

-We recommend the client avoid launching the Kickstarter between the months of October and December. 

-We recommend looking into February if the client is concerned about the amount of Kickstarter projects with concurrent launches.

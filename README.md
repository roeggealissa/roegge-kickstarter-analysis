# roegge-kickstarter-analysis
# Trend finding in Kickstarter data using Excel

### Introduction 

Kickstarter is a great website for small groups to find funding for upcoming projects. This website has the user to specify a minimum funding goal and a project deadline by which the minimum goal must be reached; if the goal is not reached the money is returned to the investors. The project we're analyzing is a play titled Fever with an initial estimated budget of around 12,000 USD and no set deadline. This report details the analysis of Kickstarter data, initial conclusions drawn, and limitations of the dataset or analysis are addressed.

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

##### Campaign Launch Date against Campaign Outcome

The client does not have a firm launch date, so using Pivot Tables and Pivot Charts we studied if there was a correlation between the date a Kickstarter is launched and the likelihood of successful funding.


![Figure 1: Month the campaign is launched in against the overall number of successes or failures.](https://github.com/roeggealissa/roegge-kickstarter-analysis/blob/a5bada078c7a4a80b96620d5bb01233834340cc6/Theater_Outcomes_vs_Launch.png)

From this graph we can draw a couple of initial conclusions. The first conclusion is that there is a correlation between launching during the mid-year months of May, June, and July and increased project success. May had the most overall successes at 111 successful Kickstarter projects. It is important to note however that overall, there are more Kickstarter projects started in those months on average, so the number of failures is also increased for those months. The average ratio of successful to failed projects throughout the data set is 1.68 projects, and this three month period has success to failure ratios for the May through July period exceeded the average.

The second conclusion that can be drawn is the months of October and December display a lower success to failure ratio. The ratio in both months falls to below the 1.68 average to 1.3 and 1.05 respectively.  This could have a variety of reasons for the correlation, such as less projects overall submitted to Kickstarter in that period, or a higher rate of failed projects compared to the average. 

The month of February is another alternative launch month. While it does not have the same high success rate of the early summer months, it does have an increase in successful projects and doesn't have the same overall submission rate of projects as the summer months.

The recommendations based on the results are as follows:

-We recommend aiming for a starting launch date between May 1st and July 31st.

-We recommend the client avoid launching the Kickstarter between the months of October and December. 

-We recommend looking into February if the client is concerned about the amount of Kickstarter projects with concurrent launches.

##### Funding Goal against Campaign Outcome

Louise has an initial estimate of the minimum funding required for Fever, so our analysis continued to determine if the launch goal would be a detriment to the overall Kickstarter. As Louise estimated a goal around 12,000 USD, looked at plays funded in the United States around similar funding goals.

![Figure 2: Binned launch goal against the percentage of camapaign sucess or failure.](https://github.com/roeggealissa/roegge-kickstarter-analysis/blob/3d1983651de1ccb00121d0d0dcaad6e194b90b36/Outcomes_vs_Goals.png)

Overall, Louise is not in a crowded funding goal category, with most projects having goals between 1000 and 4999 USD. On average for all the American plays Kickstarted, 45% are funded and 55% fail. In the monetary range Louise is looking to launch in, the percentage succeeded and failed are 54% and 46% respectively, so not statistically different than the average for this subsection of data. Reducing her budget to under 10,000 USD does not make a significant difference in terms of outcome and increasing her budget over 15,000 makes her odds of success 50/50. 

The most successful projects in the play category are either small projects with a sub 1,000 USD goal or moderately large projects between 35,000 USD and 45,000 USD. The projects most likely to fail are the over 45,000 USD budget projects and projects with a budget between 25,000 USD to 35,000 USD. 

The recommendation based on the results are as follows:

-Do not increase the budget on the Kickstarter beyond 15,000 USD.

-If possible, break the project down into chunks with launch goals of less than 5,000 USD.

##### Limitations and Additional Recommendations

Since Louisa was specifically launching plays, this dataset was beneficial due to the large number of theater and specifically play camapaigns. However, a larger dataset would be helpful to determine if the heighten successes seen in the May through July data are seen across all Kickstarters or just play Kickstarters. A deeper statistical analysis would also be useful to determine if the May through July months are the only months it's beneficial to start a campaign or if there are other months that show just as much success but may not look like it from the initial look at the graph. February, April, and August are all candidate months that may prove to have a high rate of success without as much competition with further analysis. Since errors on each datapoint were not determined, it's not possible to say if any month in which the sucess rate was higher than the failure rate is a "bad" month to launch. Another issue with the data not having errors is that it's difficult to tell if the high rates of the summer months are driven by continual success or one year in which summer Kickstarters saw a lot of success.

The possible outcome percentage versus goals was difficult to get any real information from since the bins were too large. If Louisa wants to buy an extra 1000 USD of props, we need to see how that would affect the outcome of the Kickstarter. Cutting the bins in half, eg 1000 to 2999 and 3000 to 4999, allows us to see how those fluctionations in a smaller budget like Louisa's affects the rate of success.

Some additional information from each Kickstarter that would be useful is if the campaign had stretch goals. Stretch goals are a way for a campaign to promise extra features if the minimum funding goal is exceeded and certain "reach" goals are met. The campaign goal versus outcome graph showed a preference for small scale Kickstarters, and it would be beneficial to know if their success is only because of their smaller goals or if it's a combination of a smaller initial goal plus stretch goals that keeps people pledging. Louisa may be able to launch her Kickstarter at a smaller initial goal but include stetch goals for additional items if it's demonstrated that stretch goals contribute to successful Kickstarters.

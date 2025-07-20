Sales Analyst Prompts

Initial Data Preparation Prompt
Objective: To define the structure of the aggregated_table and include a Order_Season field for seasonal grouping.
Prompt: "Create a table named aggregated_table that focuses on these fields: Order Date, Ship Date, Ship Mode, Segment, Country, City, State, Region, Category, Product Name, Sales, Quantity, Discount, Profit. Create fields that group dates by the seasons (i.e., summer, winter, fall, spring)."

Discover (D) Stage Prompt
Objective: To perform an initial comprehensive analysis of sales and profit data, identify key patterns, outliers, and preliminary business implications.
Prompt: "Analyze the sales and profit data from the aggregated_table.csv, acting as a Sales & Revenue Analyst. Provide:
Summary statistics for key financial metrics (Sales, Profit, Discount, Quantity).
Key patterns in sales performance across different dimensions (Region, Segment, Category).
Notable outliers or anomalies in Profit or Sales.
An initial assessment of business implications, specifically highlighting potential growth opportunities and factors impacting revenue generation.
Suggested next steps for deeper investigation into sales trends over time, seasonality, and potential revenue drivers."

Investigate (I) Stage Prompt
Objective: To delve deeper into observed patterns, understand underlying drivers, and perform targeted analyses using Python code.
Prompt: "I have completed the 'Discover' phase of the DIVE method, identifying sales patterns, regional/segment differences, and outliers. I now need Python code for the 'Investigate' phase to understand the underlying drivers and 'why' these patterns exist. Please generate Python code using pandas, matplotlib, and seaborn to perform the following targeted investigations:
Data Preparation: Convert the 'Order Date' column to datetime format to enable time-based analysis.
Temporal Analysis (Sales Trends and Seasonality): Aggregate the data by month to analyze sales trends over time. Create a line plot visualizing total monthly sales over the entire period to identify long-term trends. Analyze seasonality by grouping data by 'Order_Season' or extracting the month from 'Order Date', and visualize average sales per month or season to identify recurring patterns.
Revenue Drivers Analysis (Discounts and Profitability): Analyze the relationship between 'Discount', 'Sales', and 'Profit'. Generate scatter plots to visualize the impact of discounts on profitability. Calculate and visualize the Profit Margin (Profit / Sales) for each 'Category' and 'Segment' using bar plots to compare profitability across dimensions. Analyze the relationship between 'Quantity' and 'Sales'/'Profit' to understand the impact of order size.
Comparative Regional Analysis: Create visualizations (e.g., bar plots) to compare Profit performance across different 'Regions' to understand factors contributing to the lower sales observed in the South region.
Low-Profit/High-Loss Outlier Investigation: Filter the dataset to identify transactions with negative profit (losses). Identify the top products, categories, and segments contributing to the highest losses."

Validate (V) Stage Prompt
Objective: To critically review findings from the Discover and Investigate stages, assess reliability, and identify limitations or biases.
Prompt: "I have completed the Investigate phase, analyzing sales trends, seasonality, and identifying major loss contributors (products, categories, regions, and segments). I need to transition to the 'Validate' (V) stage of the DIVE method to ensure these findings are reliable and actionable. Using the Validator Pattern, please critically review the findings and analysis performed in the Discover and Investigate stages. Identify and evaluate the following:
Potential Flaws or Biases: Are there any data quality issues, sampling biases, or assumptions that might invalidate the observed trends (e.g., seasonality, discount impact, loss contributions)?
Alternative Explanations: Could the observed patterns (e.g., the low overall profit margin, the negative correlation between discounts and profit, or the high losses in specific products/categories) be explained by factors not analyzed (e.g., operational costs, returns, timing of data collection)?
Missing Data: What additional data points or variables would be necessary to strengthen the conclusions about revenue drivers and loss mitigation?
Business Logic Alignment: Do the findings align with standard business expectations for the analyzed dimensions?
Confidence Level: Assign a confidence level (High/Medium/Low) to the overall analysis regarding the identification of profit drivers and loss contributors, providing justification for the assessment."

Extend (E) Stage Prompt
Objective: To transform validated insights into actionable business value, recommending immediate, medium-term, and strategic actions.
Prompt: "I have completed the Discover, Investigate, and Validate phases of the DIVE method. The analysis identified key patterns in sales performance, highlighted significant losses in specific products (e.g., Furniture and Technology categories) and regions (e.g., Central region), and observed a negative correlation between discounts and profit. However, the analysis confidence level is 'Medium' due to the absence of critical data such as COGS and operational expenses. I am now in the 'Extend' (E) phase, focused on transforming these insights into actionable business value. Using the Strategist Pattern, recommend actions based on the current findings and validation results. Focus on improving profitability and mitigating losses:
Immediate Actions (within 1 week): What immediate steps can be taken based on the observed negative correlation between discounts and profit, and the top loss contributors?
Medium-term Initiatives (1-3 months): Outline initiatives to investigate the impact of missing data (COGS, returns, operational costs) and improve the accuracy of profit calculations.
Strategic Change (3-12 months): Recommend a long-term strategy for optimizing profitability in the high-loss categories (Furniture, Office Supplies, Technology) and regions (Central, East).
Future Investigations: Based on the limitations identified in the Validate phase, specify the follow-up analysis needed.
KPIs and Success Metrics: What Key Performance Indicators (KPIs) should be monitored to track the success of these recommendations?
Estimated Impact and Required Resources: For each recommendation, provide an estimated impact (e.g., cost savings, revenue growth, efficiency gains) and the required resources."

Customer Analyst Prompts

Prompt # Phase Query Type Gemini Prompt Gemini Response

1 Discover Initial Observation - General Inquiry

Using the dataset, provide Initial Observations that will help me
understand Consumer Behavior for a retail store.

Guided to focus on key metrics and initial segment/profit
observations.

2 Discover Initial Observation - Specific Metric

What states/cities contribute most to sales and profit

Included in initial data overview and highlighted critical negative
profit cities.

3 Discover Initial Observation - Specific Metric

Are there segments with high sales but low profit

Identified Home Office as high profit per sale, Consumer as high
volume.

4 Discover Initial Observation - Preference

Which customer segments or shipping preferences drive the
most sales/profit

Identified customer segments, prepared to investigate shipping
later.

5 Discover Schema Analysis

Analyze the schema of the table and identify the top 5 most
interesting patterns or observations.

Used user's executive summary for initial findings and schema
context.

6 Discover Critical Questions

What 3 critical questions would you used to answer about
customer purchasing patterns

Connected to assignment's focus questions: most valuable,
purchasing patterns, retention.

7 Investigate Deep Analysis - General Inquiry Deep Analysis: Who are our most valuable customers? Guided towards CLTV indicators and segment profitability.
8 Investigate Deep Analysis - General Inquiry

How can we improve customer retention

Connected to analyzing unprofitable customers and segment
strategies.

9 Investigate Hypothesis Generation

Do customers with high Total Sales also have high Total Orders
count, or do they just make a very large purchase

Prompted to investigate AOV and purchase frequency per
customer.

10 Investigate Customer Activity Inquiry Who are the most recent actively customers Guided to calculate Recency as part of CLTV indicators.
11 Investigate Customer Activity Inquiry Are there customers who spent a lot but haven’t purchased Guided to identify At-Risk High-Value customers via CLTV.
12 Investigate Hypothesis Generation

What are 5 possible business explanations for why some
customers have very high total sales but haven’t purchased

Focused on retention, leading to CLTV investigation.

13 Investigate Hypothesis Generation

Generate 3 hypotheses for the correlation between sales and
profit, considering customer behavior

Addressed by analyzing discount impact on profit in
cities/products.

14 Investigate Why Question

What factors could cause customer sales to vary significantly?
List 3 possibilities.

Led to investigation of segment and product performance.
15 Investigate Specific Analysis Request Do categories with high sales in these cities also show negative Addressed by Query 1 (profit by city) and Query 3 (product
16 Investigate Specific Analysis Request

Is there a specific category with very high Quantity Sold but
low/negative profit, suggesting a potential issue

Addressed by Query 3 on product profit for cities and by
segment.

17 Investigate Hypothesis Generation

What are 5 possible operational or customer behavior reasons
for high sales byt negative profit, and what could be the

Led to alternative explanations: high returns, hidden costs,
discounting.

18 Investigate Analytical Concept

Explain what Recency, Frequency, and Monetary (RFM) analysis
means for customer behavior in a retail context.

Concept explained; applied through CLTV query metrics.

19 Investigate Hypothesis Generation

Generate 3 hypotheses about the typical purchasing patterns of
customers in the 'Consumer' segment versus the 'Corporate'

Addressed by segment AOV/profit and product profitability by
segment queries.

20 Investigate Hypothesis Generation

What are some common hypotheses for why the Home Office
segment has higher profit margins in retail?

Addressed by segment AOV/profit and product profitability by
segment queries.

21 Investigate Specific Analysis Request

What is the average profit and sales per order in these
problematic cities, and how do they compare to profitable

Provided Query 1 for City Profitability Analysis.

22 Investigate Specific Analysis Request

What is the average discount rate in these problematic cities vs.
profitable ones?

Provided Query 2 for City Discount Rate Analysis.
23 Investigate Specific Analysis Request Which product categories are contributing most to losses in Provided Query 3 for Product Profitability by City.
24 Investigate Specific Analysis Request

What is the average order value (AOV) and average profit per
order for each segment

Provided Query 1 for Segment Performance.

25 Investigate Specific Analysis Request

What are the top-selling (by sales) and most profitable product
categories for each segment?

Provided Query 2 for Product Profitability by Segment (later
corrected to Product ID).
26 Investigate Specific Analysis Request Calculate Total Sales, Total Profit, and Number of Orders per Provided Query for CLTV Indicators.
27 Investigate Data Review Question

Look at Average_Discount_Rate. Is there a noticeable trend of
higher discounts in the unprofitable cities?

Confirmed and interpreted Query 2 (City Discount Rate) results.

28 Investigate Data Review Question

How do the Avg_Order_Value and Avg_Profit_Per_Order compare
across Consumer, Corporate, and Home Office?

Confirmed and interpreted Query 1 (Segment Performance)
results.

29 Investigate Data Review Question

What are the most profitable Product_Categories for each
segment? Are there specific categories that stand out?

Interpreted Query 2 (Product Profit by Segment) results.

30 Investigate Analysis Focus Shift

Look for customers who have large negative
Product_Profit_By_Unprofitable_Customer. Are these primarily
Office Supplies or Furniture items?

Provided Query 1 for Unprofitable Customer Product Patterns.

31 Investigate Analysis Focus Shift

See if certain Ship Modes (e.g., Standard Class, First Class)
consistently lead to negative profit for these customers.

Provided Query 2 for Unprofitable Customer Ship Mode Usage.

32 Validate Request for Alternative Explanations

look for no more than 2 potential alternative explanations. Note
that these are the only field names available, so we must stick to
those: [schema provided]

Provided 2 alternative explanations (high shipping costs/ship
mode, higher returns) and schema limitations.

Product Analyst Prompts

can i connect to myproj5900.lab1_eda.lab1_eda
Yes, you can connect to your BigQuery table myproj5900.lab1_eda.lab1_eda. Here is the code to connect to the table and display the first few rows.

#### Top Products by Total Sales SELECT product_name, SUM(sales) AS total_sales, SUM(profit) AS total_profit, AVG(profit_margin) AS avg_profit_margin, SUM(quantity) AS total_quantity FROM myproj5900.lab1_eda.lab1_eda GROUP BY product_name ORDER BY total_sales DESC LIMIT 10;
Here is the code to run the query.
It seems the client object was not defined. I will add the necessary code to initialize it and then execute the query again.
The query executed successfully, and here are the top 10 products by total sales.
Would you like to explore the products with the lowest profit margin, or perhaps visualize the sales distribution across different categories?

what is Top Products by Total Sales
This query retrieves the top 10 products based on their total sales from the myproj5900.lab1_eda.lab1_eda table in BigQuery. It calculates the sum of sales, sum of profit, average profit margin, and sum of quantity for each product, groups the results by product name, and then orders them in descending order of total sales, limiting the output to the top 10.

query for Top Products by Total Sales
Here is the SQL query for "Top Products by Total Sales":

query and run Top Products by Total Sales
I have already executed the query for the Top Products by Total Sales in the previous turn. You can find the results in the output of cell eda5a151.

query and run Category Performance Ranking
I can help with that. I will generate a query and the code to run it for "Category Performance Ranking".
The query for Category Performance Ranking has been executed, and the results are displayed.
Would you like to visualize these results, or perhaps delve deeper into the performance of subcategories within each category?

What drives product profitability?
That's a great question to explore! To understand what drives product profitability, we can analyze several factors. Here is a plan to investigate this:
Analyze existing data: Examine the existing data, particularly focusing on the profit, sales, quantity, discount, and profit_margin columns, to identify initial correlations.
Investigate the impact of discount: Analyze how the discount column affects profit and profit_margin. This could involve grouping data by discount levels and comparing profitability metrics.
Analyze the impact of quantity: Investigate the relationship between quantity sold and profit or profit_margin. This could involve looking at product performance at different sales volumes.
Explore the impact of category and subcategory: Analyze if certain category or subcategory have higher or lower average profit margins.
Examine the effect of region: Investigate if region plays a role in product profitability.
Look into the influence of customer and manufactory: Analyze if certain customer or manufactory are associated with higher or lower profitability.
Visualize findings: Create visualizations to illustrate the relationships discovered in the analysis (e.g., scatter plots of discount vs. profit margin, bar charts of average profit margin by category).
Summarize key drivers: Based on the analysis, summarize the key factors that appear to drive product profitability.
Finish task: Present the findings in a clear and understandable format.
Generating...
Preparing
Analyze existing data
Investigate the impact of discount
Analyze the impact of quantity
Explore the impact of category and subcategory
Examine the effect of region
Look into the influence of customer and manufactory
Visualize findings
Summarize key drivers
Finish task

what is Profit Margin by Product
Here is the query to get the profit margin by product and the code to run it.
I have successfully retrieved and displayed the average profit margin for each product.
Would you like to continue with the plan to analyze the key drivers of product profitability, or is there anything else you would like to explore regarding product profit margins?

what is Profitability vs. Discount
I have already analyzed the relationship between profitability and discount in a previous step. The results showing the average profit and average profit margin for different discount levels are available in the output of cell 3280c110.

Where should we focus product strategy?
Based on the analysis of the data, here are some key areas where you could focus your product strategy:
Minimize Discounts: Products with higher discounts tend to have significantly lower profit margins. Focus on reducing discounts, especially for products that already have low profitability.
Promote High-Margin Categories and Subcategories: The analysis showed that categories like 'Technology' and subcategories such as 'Labels', 'Paper', and 'Envelopes' have higher average profit margins. Consider focusing sales and marketing efforts on these areas.
Address Low-Margin Categories and Subcategories: Subcategories like 'Tables', 'Bookcases', and 'Binders' have negative average profit margins. Investigate the reasons for this and consider strategies to improve their profitability or potentially de-emphasize them.
Regional Focus: The West region shows the highest average profit margin, while the Central region has a negative average profit margin. Tailor your sales and marketing strategies to the profitability characteristics of each region.
Customer and Manufactory Analysis: Some customers and manufactories are associated with higher or lower profitability. Further analysis into these relationships could inform targeted sales approaches and supplier negotiations.
These insights are summarized in markdown cell 3bbfde96.

what queries should i use to better understand where we should focus our product strategy?
That's a great question! To further refine where to focus your product strategy, you could consider queries that explore the interactions between the factors we've already analyzed. Here are some examples of queries that could provide deeper insights:
Profitability by Region and Category: This query would show you which categories are most profitable within each region.
SELECT region, category, AVG(profit_margin) AS average_profit_margin
FROM `myproj5900.lab1_eda.lab1_eda`
GROUP BY region, category
ORDER BY region, average_profit_margin DESC
Profitability by Discount Level and Category: This query could reveal if certain categories are more sensitive to discounts than others.
SELECT category, discount, AVG(profit_margin) AS average_profit_margin
FROM `myproj5900.lab1_eda.lab1_eda`
GROUP BY category, discount
ORDER BY category, discount
Top Profitable Products within Low-Margin Subcategories: This query could help identify outlier products that are profitable even within generally low-margin subcategories.
SELECT product_name, AVG(profit_margin) AS average_profit_margin
FROM `myproj5900.lab1_eda.lab1_eda`
WHERE subcategory IN ('Tables', 'Bookcases', 'Binders') -- Example low-margin subcategories
GROUP BY product_name
ORDER BY average_profit_margin DESC
LIMIT 10
Would you like me to generate the code to run any of these queries?

yes
Great! I will generate the code to run the first query to see the profitability by region and category.
The query for Profitability by Region and Category has been executed, and the results are displayed.
Would you like to run the other suggested queries to explore profitability by discount and category, or identify profitable products within low-margin subcategories? Alternatively, we can proceed with summarizing all the findings to help you focus your product strategy.

what are High Profit, Low Return/Discount Products
I can help you with that. Here is a query to find products with high profit and low discount, which could be considered "High Profit, Low Return/Discount Products". I'll define "high profit" as having a profit greater than the average profit and "low discount" as having a discount of 0.
The query for High Profit, Low Return/Discount Products has been executed, and the results are displayed. These are products with a profit above the average profit and no discount applied.
Would you like to explore these products further, such as their categories or regions, or shall we proceed with summarizing the key drivers of profitability based on all the analyses we've performed?

what is the profitability for each product?
I have already calculated the average profit margin for each product in a previous step. You can find the results in the dataframe df_product_profit_margin.

can you provide a comparison for performance of each product?
Yes, I can provide a comparison for the performance of the top products based on the data we have. The df dataframe contains the following metrics for the top products by total sales:
total_sales
total_profit
avg_profit_margin
total_quantity
Displaying df will show you these performance indicators for each of the top products:
The performance comparison for the top products by total sales is displayed above, showing their total sales, total profit, average profit margin, and total quantity.
Would you like to explore the performance of products based on other criteria, such as those with the highest profit margins, or would you like to continue with summarizing the key drivers of profitability?

Can you include what the difference to average profitability?
Yes, I can modify the query to include the difference from the overall average profitability for each product.
I have updated the query and the results now include the difference in average profit margin for each product compared to the overall average.
Would you like to explore products that have a significant positive or negative difference from the average, or should we proceed with summarizing all the findings to understand the key drivers of profitability?

what is the discount Impact on Product Success
Based on the analysis we performed (in cell 3280c110), we can see that discount has a significant impact on product profitability. As the discount percentage increases, the average profit and average profit margin generally decrease. Products with no discount tend to have the highest average profit and profit margin. This suggests that while discounts might drive sales volume (which we haven't specifically analyzed for this question), they negatively impact the profitability of individual transactions.
You can review the results of this analysis in the output of cell 3280c110.

how do i export my prompts?
Your prompts are part of the notebook's input cells. To export your prompts, you can save the entire notebook. Go to the "File" menu in Colab, and select "Download". You can choose to download the notebook in .ipynb format (Jupyter Notebook) or .py format (Python script). Both formats will include your prompts as part of the saved file.

Regional Analyst Prompts

Connect to mgmt599-molneeric.mgmt599_data.superstore

Aggregate data by grouping the following columns 'Order ID', 'Order Date', 'Ship Date', 'Ship Mode', 'Customer ID', 'Customer Name', 'Segment', 'Country', 'City', 'State', 'Postal Code', 'Region'

Add metrics Days to Ship by calculating the number of days between Order Date and Ship Date

Create performance metrics by Region, State, and City and include profit to sales ratio

Identify the top and bottom performing locations

What operational factors impact the performance metrics?

Analyze the quality of data and perform statistical significance testing against the "mgmt599-molneeric.mgmt599_data.agg_superstore" table.

Assess the quality of theagg_superstore_df, including checking for missing values, duplicates, and inconsistencies in data types or formats.

Select the appropriate statistical test(s) based on the type of data and the questions being asked (e.g., t-tests, ANOVA, chi-squared tests).

Execute the chosen statistical tests on the selected variables.

Analyze the output of the statistical tests to determine if the results are statistically significant and what they imply.

Summarize the findings from the data quality analysis and statistical significance testing.
Analyze Operational Factors for High-Sales,

Low-Profit Locations

Analyze Operational Factors for High-Sales,
High-Profit Locations

Compare Operational Factors between High-Sales, Low-Profit and High-Sales, High-Profit Locations


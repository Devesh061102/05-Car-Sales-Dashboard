# Car Sales Dashboard - Power BI
![Dashboard](https://github.com/Devesh061102/05_Car_Sales_Dashboard/blob/main/Screenshots/Screenshot%202024-05-24%20111328.png?raw=true)

![Dashboard](https://github.com/Devesh061102/05_Car_Sales_Dashboard/blob/main/Screenshots/Screenshot%202024-05-24%20111427.png?raw=true)
## Problem Statement

### Background
Our company is a car dealership that sells various car models. To effectively track and analyze our sales performance, we need a comprehensive Car Sales Dashboard in Power BI.

### Objective
The objective of this project is to design and develop a dynamic and interactive Car Sales Dashboard using Power BI. The dashboard will visualize critical KPIs related to our car sales, helping us understand our sales performance over time and make data-driven decisions.

## Problem Statement 1: KPIs Requirement
The dashboard should provide real-time insights into key performance indicators (KPIs) related to our sales data. This will enable us to make informed decisions, monitor our progress, and identify trends and opportunities for growth.

## Solution 
Calendar Table is an extra table created which contains the Data,Month,Week,Day Columns and linked to the main Car_data dable throught data column in a one to many link from Calendar Table to Car Table.

### Sales Overview
1. **Year-to-Date (YTD) Total Sales**
   - **Measure**: `TOTALYTD(SUM(car_data[Price ($)]), 'Calendar Table'[Date])`
   - **Value**: $371,185,120
   - **Explanation**: Provides an overall picture of revenue generated from the beginning of the year up to the current date.

2. **Month-to-Date (MTD) Total Sales**
   - **Measure**: `TOTALMTD(SUM(car_data[Price ($)]), 'Calendar Table'[Date])`
   - **Value**: $54,281,601
   - **Explanation**: Shows the sales figures for the current month, giving a snapshot of recent performance.

3. **Year-over-Year (YOY) Growth in Total Sales**
   - **Measures**: 
     - `PYTD Total Sales = CALCULATE(SUM(car_data[Price ($)]), SAMEPERIODLASTYEAR('Calendar Table'[Date]))`
     - `YOY Sales Growth = [Sales Difference] / [PYTD Total Sales]`
   - **Value**: 23.59%
   - **Explanation**: Measures the percentage increase in sales compared to the same period in the previous year, indicating growth trends.

4. **Difference between YTD Sales and Previous Year-to-Date (PTYD) Sales**
   - **Measure**: `Sales Difference = [YTD Total Sales] - [PYTD Total Sales]`
   - **Value**: $70,844,775
   - **Explanation**: Compares the current year's YTD sales with the previous year's YTD sales, highlighting changes in performance.


![Sales Price Analysis](https://github.com/Devesh061102/05_Car_Sales_Dashboard/blob/main/Screenshots/Screenshot%202024-05-23%20213159.png?raw=true)

### Average Price Analysis
1. **YTD Average Price**
   - **Measure**: `TOTALYTD([Avg Price], 'Calendar Table'[Date])`
   - **Value**: $27,990.7
   - **Explanation**: The average selling price of cars from the beginning of the year to the current date, reflecting pricing trends.

2. **MTD Average Price**
   - **Measure**: `TOTALMTD([Avg Price], 'Calendar Table'[Date])`
   - **Value**: $28,256.95
   - **Explanation**: The average price of cars sold in the current month, useful for understanding recent pricing strategies.

3. **YOY Growth in Average Price**
   - **Measures**: 
     - `PYTD Avg Price = CALCULATE([Avg Price], SAMEPERIODLASTYEAR('Calendar Table'[Date]))`
     - `YOY Avg Price Growth = [Avg Price Diff] / [PYTD Avg Price]`
   - **Value**: -0.79%
   - **Explanation**: Measures the percentage change in the average price of cars compared to the same period in the previous year, indicating pricing trends.

4. **Difference between YTD Average Price and PTYD Average Price**
   - **Measure**: `Avg Price Diff = [YTD Avg Price] - [PYTD Avg Price]`
   - **Value**: -$223.48
   - **Explanation**: Compares the average price of cars sold in the current year to the same period in the previous year, highlighting changes in pricing.

![Average Price Analysis](https://github.com/Devesh061102/05_Car_Sales_Dashboard/blob/main/Screenshots/Screenshot%202024-05-23%20213256.png?raw=true)

### Cars Sold Metrics
1. **YTD Cars Sold**
   - **Measure**: `TOTALYTD(COUNT(car_data[Car_id]), 'Calendar Table'[Date])`
   - **Value**: 13,261
   - **Explanation**: Counts the total number of cars sold from the beginning of the year to the current date, providing insight into sales volume.

2. **MTD Cars Sold**
   - **Measure**: `TOTALMTD(COUNT(car_data[Car_id]), 'Calendar Table'[Date])`
   - **Value**: 1921
   - **Explanation**: The total number of cars sold in the current month, reflecting recent sales activity.

3. **YOY Growth in Cars Sold**
   - **Measures**: 
     - `PYTD Cars Sold = CALCULATE(COUNT(car_data[Car_id]), SAMEPERIODLASTYEAR('Calendar Table'[Date]))`
     - `YOY Cars Sold Growth = [Cars Sold Diff] / [YTD Cars Sold]`
   - **Value**: 19.73%
   - **Explanation**: Indicates the percentage increase in the number of cars sold compared to the same period in the previous year, showing growth in sales volume.

4. **Difference between YTD Cars Sold and PTYD Cars Sold**
   - **Measure**: `Cars Sold Diff = [YTD Cars Sold] - [PYTD Cars Sold]`
   - **Value**: 2,616
   - **Explanation**: Compares the number of cars sold in the current year to the same period in the previous year, highlighting changes in sales volume.


![Cars Sold Metrics](https://github.com/Devesh061102/05_Car_Sales_Dashboard/blob/main/Screenshots/Screenshot%202024-05-23%20213331.png?raw=true)

## Problem Statement 2: Charts Requirement

1. **YTD Sales Weekly Trend**: Line chart showing weekly YTD sales.
2. **YTD Total Sales by Body Style**: Donut chart displaying YTD sales by car body style.
3. **YTD Total Sales by Color**: Donut chart presenting YTD sales by car color.
4. **YTD Cars Sold by Dealer Region**: Bar chart visualizing YTD sales distribution by dealer region.
5. **Company-Wise Sales Trend in Grid Form**: Tabular grid with company names and their YTD sales figures.
6. **Details Grid Showing All Car Sales Information**: Detailed grid with car model, body style, color, sales amount, dealer region, date, and other relevant information.

## Solution 

1. **YTD Sales Weekly Trend**

![Line Chart](https://github.com/Devesh061102/05_Car_Sales_Dashboard/blob/main/Screenshots/Screenshot%202024-05-23%20213408.png?raw=true)

   - **Visual**: Line Chart
   - **Details**: Display the weekly trend of YTD sales with the X-axis representing weeks and the Y-axis showing total sales amount.
   - **Insights**: Car sales typically exhibit a marked increase after week 30. The beginning of the year tends to perform poorly with notably lower sales figures until mid-year. Notably, weeks 30 to 53 see a peak in sales for most car brands, indicating a seasonal impact on car sales.

3. **YTD Total Sales by Body Style**
   
![Donut Chart](https://github.com/Devesh061102/05_Car_Sales_Dashboard/blob/main/Screenshots/Screenshot%202024-05-23%20213435.png?raw=true)

   - **Visual**: Donut  Chart
   - **Details**: Visualize the distribution of YTD total sales across different car body styles.
   - **Insights**: SUVs are the most preferred body style, accounting for 26.91% of total sales, while hardtops are the least preferred with only 13.85%. SUVs are favored for their visibility, comfort, space, safety features, and suitability as family cars.

5. **YTD Total Sales by Color**
   
![Donut Chart](https://github.com/Devesh061102/05_Car_Sales_Dashboard/blob/main/Screenshots/Screenshot%202024-05-23%20214402.png?raw=true)

   - **Visual**: Donut  Chart
   - **Details**: Present the contribution of various car colors to the YTD total sales.
   - **Insights**: Pale white is the most popular color among car buyers, with 47.02% of cars sold in this color. White cars stay cooler in hot climates, are perceived as clean and modern, and show dirt and scratches less visibly than darker colors.

7. **YTD Cars Sold by Dealer Region**
   
![Bar Chart](https://github.com/Devesh061102/05_Car_Sales_Dashboard/blob/main/Screenshots/Screenshot%202024-05-23%20214430.png?raw=true)

   - **Visual**: Bar Chart
   - **Details**: Showcase the YTD sales data based on different dealer regions to visualize sales distribution.
   - **Insights**: Regions such as Austin and Janesville stand out with sales exceeding $100 million, while regions like Scottsdale, Aurora, Greenville, Pasco, and Middletown have sales figures ranging between $85 million and $100 million.

9. **Company-Wise Sales Trend in Grid Form**
    
![Table](https://github.com/Devesh061102/05_Car_Sales_Dashboard/blob/main/Screenshots/Screenshot%202024-05-23%20214455.png?raw=true)

   - **Visual**: Table
   - **Details**: Provide a tabular grid displaying the sales trend for each company, showing company names along with their YTD sales figures.
   - **Insights**:
     - Cadillac has the highest YTD average price at $42.2K, reflecting its premium positioning.
     - Hyundai records the lowest YTD average price at $19.1K, indicating its competitive pricing strategy.
     - Chevrolet leads in YTD cars sold with 1,043 units, underscoring its strong market presence.
     - Jaguar, despite a comparable average price of $24.5K, sold only 102 cars YTD, highlighting brand perception's impact on sales.
     - Chevrolet contributes 7.3% of total sales, indicating a significant market share.

11. **Details Grid Showing All Car Sales Information**
    
![Table](https://github.com/Devesh061102/05_Car_Sales_Dashboard/blob/main/Screenshots/Screenshot%202024-05-23%20214612.png?raw=true)

   - **Visual**: Table
   - **Details**: Create a detailed grid presenting all relevant information for each car sale, including car model, body style, color, sales amount, dealer region, date, etc.
   - **Insights**:
     - The highest single-day sales peak at approximately $85K, recorded by brands such as Cadillac, Toyota, Audi, and Mercedes-Benz.
     - Cumulative sales across all companies over two years amount to approximately $671 million.


## Conclusion
In conclusion, the Car Sales Dashboard developed in Power BI provides a comprehensive and dynamic overview of our dealership's sales performance. By incorporating critical KPIs and visualizations, the dashboard delivers valuable insights into various aspects of car sales, including sales trends, average prices, and the distribution of cars sold across different regions, body styles, and colors.

### Key Takeaways:
**Enhanced Sales Tracking**: The dashboard enables real-time tracking of key sales metrics, such as Year-to-Date (YTD) and Month-to-Date (MTD) sales, along with Year-over-Year (YOY) growth. This allows for timely and informed decision-making to optimize sales strategies.

**In-depth Price Analysis**: Average price metrics provide a clear understanding of pricing trends, helping to identify opportunities for pricing adjustments and maximizing profitability.

**Comprehensive Sales Distribution**: The visualizations highlight significant patterns and preferences in body styles and colors, offering insights into consumer behavior and guiding inventory management decisions.

**Geographical Insights**: Sales data broken down by dealer region reveals regional performance variations, aiding in targeted marketing and sales efforts to improve regional sales outcomes.

**Detailed Performance by Company**: The tabular grids present detailed information on sales trends for each company, as well as comprehensive data on individual car sales, ensuring a thorough understanding of overall sales performance and company-specific achievements.

### Future Enhancements:
**Real-Time Data Integration**: Implementing real-time data integration to ensure that the dashboard always reflects the most current sales information.

**Advanced Predictive Analytics**: Incorporating predictive analytics to forecast future sales trends and identify potential market opportunities.

**Customer Demographics Analysis**: Adding customer demographics data to gain deeper insights into the target audience and tailor marketing strategies accordingly.

The Car Sales Dashboard serves as a powerful tool for our dealership, enabling us to monitor and analyze sales performance efficiently. By leveraging these insights, we can make data-driven decisions that drive growth, improve customer satisfaction, and strengthen our market position.

## Lessons Learned

- **Data Preparation is Critical** : Ensuring data quality and completeness is the foundation of any data analysis project. This project taught you the importance of thoroughly cleaning and validating data before performing any analysis. Proper data preparation can prevent inaccuracies and lead to more reliable insights.
- **Defining and Calculating KPIs** : Identifying and calculating key performance indicators (KPIs) such as YTD sales, MTD sales, and YOY growth are crucial for monitoring performance. This project emphasized the need to define clear, relevant KPIs that align with business goals, allowing for targeted analysis and decision-making.
- **Mastering DAX for Advanced Calculations** : Learning to use Data Analysis Expressions (DAX) for creating complex measures was an essential part of this project. DAX provides powerful functions to manipulate and analyze data, and mastering it can significantly enhance your ability to derive meaningful metrics from raw data.
- **Effective Data Visualization** : Choosing the right visualization techniques (e.g., line charts, pie charts, bar charts) to represent data is key to communicating insights effectively. This project highlighted the importance of visual design in making data understandable and actionable for stakeholders.
- **Iterative Learning and Improvement** : As my first project in Power BI, it provided a valuable learning experience in using Power BI. I learned to handle various aspects of data analysis and visualization, and each step helped me to  grow more proficient. 

## Authors

- [@Devesh](https://github.com/Devesh061102)

# Hi, I'm Devesh! 👋


## 🚀 About Me
I'm a Full Stack Data Scientist


## 🛠 Skills
1. C, C++, Python
2. SQL
3. Machine Learning
4. Deep Learning
5. Data Science

# Airlines_Business_Project  
![Airline_project_logo](https://github.com/priyankachaurasiaa/Airlines_Business_Optimization_Project/assets/134799886/1a6c1332-c022-47e0-ba3b-c0186396f1c0)

"ElevateAir: Enhancing Aviation Profitability via Data-Driven Occupancy Optimization"

ElevateAir addresses modern aviation challenges by analyzing our diverse aircraft fleet's occupancy rates. 
Strict regulations, rising costs and market competition compel us to boost profitability. 
Through as an insightful data analysys, we aim to optimize seat occupancy, elevating both passenger experiences and per-seat profits. 
Join us in shaping aviation's future through innovation and data excellence.

## Table of Contents
- [Introduction](#introduction)
- [Installation and Steps Involved](#installation-and-steps-involved)
- [Objectives](#objectives)
- [Schema](#schema)
- [Database and Tables](#database-and-tables)
- [Preprocessing and Exploration](#preprocessing-and-exploration)
- [Analysis and Insights](#analysis-and-insights)
- [Conclusion](#conclusion)

## Introduction
- Navigating Aviation Challenges: Our aviation fleet thrives on passenger satisfaction. Yet, factors like regulations, costs, and competition challenge profitability.
- Data-Powered Solution: Through precise data analysis, we're optimizing seat occupancy to counter financial pressures and offer exceptional travel.
- Revitalizing Industry: This project not only boosts per-seat profits but also revolutionizes aviation economics, inviting you to shape a sustainable future with us.  

## Installation and Steps Involved
<pre><code>
1. Google Colab Setup:
  Open Google Colab.
  Create a new notebook or import your existing notebook.
  
2. Google Drive Integration:
  Mount Google Drive to access project files: from google.colab import drive and drive.mount('/content/drive').

3. Library Imports:
  ```python
  import sqlite3
  import numpy as np
  import pandas as pd
  import matplotlib.pyplot as plt
  import seaborn as sns'''

4. Data Loading:
	Load data into Colab environment.
	If using SQLite: conn = sqlite3.connect('your_database.db').

5. Data Exploration:
	Use Pandas for data analysis: df = pd.read_sql_query("SELECT * FROM your_table", conn).

6. Data Visualization:
	Create visualizations using Matplotlib and Seaborn: plt.plot(...), sns.barplot(...), etc.

7. Analysis and Insights:
	Analyze data patterns, trends, and correlations.
	Extract insights from your data exploration.

8. Project Completion:
	Save and download your modified notebook to your local drive.
</code></pre>

## Objectives
*Increase Occupancy Rate:*
  -The primary objective is to raise the occupancy rate. Achieving this will directly enhance the average profit per seat, countering the current challenges.

*Optimize Pricing Strategy:*
-Develop a dynamic pricing strategy that adapts to market fluctuations and aligns with customer preferences. This will attract and retain customers effectively.

*Elevate Customer Experience:*
-Prioritize a seamless end-to-end experience for passengers, from booking to arrival. This distinctiveness in a competitive industry will foster customer loyalty.

* The ultimate aim of these objectives is to pinpoint avenues for boosting the occupancy rate on flights with lower performance. 
This targeted effort has the potential to significantly amplify the airline's profitability.

## Schema  
![Schema](https://github.com/priyankachaurasiaa/Airlines_Business_Optimization_Project/assets/134799886/ae4de0b2-b85f-4931-b899-9166dfa3725a)

## Database and Tables
 <pre><code>
**List of tables in Database:**
''' ['aircrafts_data',
 'airports_data',
 'boarding_passes',
 'bookings',
 'flights',
 'seats',
 'ticket_flights',
 'tickets']'''
</code>  </pre>

## Preprocessing and Exploration

**Null and Noise Handling:** Conducted a thorough assessment to identify and address null values in the dataset. Also, implemented noise reduction techniques to ensure data accuracy.

**Data Type Consistency:** Ensured uniform data types across the dataset. This consistency aids in smooth processing and analysis.

**Table Size and Shape Evaluation:** Assessed the size and shape of each table to comprehend its structure. This step is crucial for understanding the data's composition.

* By executing these preprocessing steps, the dataset was refined, cleaned, and made ready for further analysis, establishing a solid foundation for accurate insights.

## Analysis and Insights
 <pre><code>
**Basic Analysis**
Q1.How many planes have more than 100 seats?
Q2. What are the ranges of different airplane models?
Q3.How the number of tickets booked and total amount earned changes with the time?
Q4.Calculate the average charges for each aircraft with different fare conditions?

**Analysing Occupancy Rate**
Q5. For each aircraft, calculate the total revenue per year and the average revenue per ticket.
Q6. Calculate the average occupancy per aircraft. (occupanct_rate = booked_seat/available_seat)
Q7. Calculate by how much the total annual turnover could increase by giving all aircraft a 10% higher occupancy rate.
</code> </pre>

**Number of Tickets Booked with Time**  
`plt.figure(figsize=(18,6))`  
`x = df3.groupby('date')[['date']].count()`  
`plt.plot(x.index, x['date'], marker='^')`  
`plt.title('Number of tickets booked with time')`  
`plt.xlabel('Date')`  
`plt.ylabel('No of tickets')`  
`plt.grid('b')`  
`plt.show()`  

![No_of_ticket_booked_with_time](https://github.com/priyankachaurasiaa/Airlines_Business_Optimization_Project/assets/134799886/ff26a97c-ea09-4f75-8a8d-2b28094ee530)

**Total Amount Earned with Time**  
`plt.figure(figsize=(18,6))`  
`y = df3.groupby('date')[['total_amount']].sum()    # to get into dataframe use 2D list`  
`plt.plot(y.index, y['total_amount'], marker='^')`  
`plt.title('Total amount earned with Time')`  
`plt.xlabel('Date')`  
`plt.ylabel('Total amount')`  
`plt.grid('b')`  
`plt.show()`  
![Total_amount_earned_with_time](https://github.com/priyankachaurasiaa/Airlines_Business_Optimization_Project/assets/134799886/14737a85-1ed2-4f23-8e15-4e15369d2323)

**Airplane Model with Ranges**  
`plt.figure(figsize=(10,5))`  
`ax = sns.barplot(x='model',y='range', data=aircrafts_data, palette = 'Paired')`  
`for i in ax.containers:`  
`    ax.bar_label(i)`  
`plt.title('Airplane Models with their Ranges')`  
`plt.xticks(rotation=45)`  
`plt.show()`  
![Airplane_Model_with_Ranges](https://github.com/priyankachaurasiaa/Airlines_Business_Optimization_Project/assets/134799886/77626aac-d5cc-472c-9c56-42e62828a8d9)

**Aircraft Code vs Average Charges**  
`sns.barplot(data=df4, x=df4['aircraft_code'], y=df4['average'], hue=df4['fare_conditions'])`  
`plt.title('Aircraft code vs Average charges with different Fare conditions')`
![Aircraft_code_vs_avg_charges](https://github.com/priyankachaurasiaa/Airlines_Business_Optimization_Project/assets/134799886/0263c584-3c11-456a-bcf1-8f55a088fbed)

**Final Results**
![Final_results](https://github.com/priyankachaurasiaa/Airlines_Business_Optimization_Project/assets/134799886/ec537a99-478e-4ee3-a2c9-2c8ebc7c0c26)

**Graphical Comparison:**
- Utilized bar graphs to visually compare average costs across different fare conditions per aircraft.
- Created a bar chart to visualize and compare the ranges of different airplanes.

**Fare Types:**
- Observed three fare types: business, economy, and comfort. Comfort class is unique to the 773 aircraft, while CN1 and CR2 planes exclusively offer economy class.

**Price Comparison:**
- Noted a consistent pattern where business class charges consistently exceeded economy class charges across all aircraft.

**Revenue Analysis for Profit Maximization:**
- Examining overall yearly income and average revenue per ticket is crucial for airlines to optimize profitability.
- Insights from these metrics guide decisions on aircraft types, itineraries, pricing optimization, and resource allocation.

**Revenue and Occupancy Impact:**
- Total revenue, average revenue per ticket, and average occupancy per aircraft are critical indicators.
- SU9 aircraft leads in total revenue with lower business and economy class prices.
- CN1 has lower revenue due to offering only economy class at a minimal price.

**Occupancy's Role in Revenue:**
- Average occupancy per aircraft reflects how effectively seats are filled.
- Higher occupancy rates improve revenue, profitability, and operational efficiency.
- Calculated by dividing booked seats by total seats.

## Conclusion  

**Revenue Data Analysis for Profitability:**
- Analyzing total yearly revenue, average ticket revenue, and aircraft occupancy is vital for maximizing airline profitability.
- Insights from these metrics guide pricing, route adjustments, and operational improvements.

**Occupancy's Role in Profitability:**
- Greater occupancy rates enhance profitability by maximizing revenue and minimizing vacant seat costs.
- Pricing adjustment based on aircraft condition and facility is crucial for attracting passengers without compromising on quality.

**Balancing Profit and Quality:**
- While boosting occupancy is crucial, maintaining customer satisfaction and safety is equally important.
- Airlines should adopt a data-driven approach to revenue analysis and optimization for sustainable success in a competitive industry.

* These summary points underscore the importance of revenue analysis, the role of occupancy in profitability, and the need to balance profit goals with delivering quality service and safety.

|---------------------------------------------------------------------------------------------------------------------------|

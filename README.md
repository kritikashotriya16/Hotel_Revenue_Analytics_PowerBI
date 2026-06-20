# Hotel_Revenue_Analytics_PowerBI
Hotel Revenue Analytics Dashboard built in Power BI using 119K+ real hotel booking records. The project analyzes key hospitality KPIs, including Revenue, ADR, RevPAR, Occupancy Rate, Cancellation Rate, and Lead Time. Designed with advanced DAX, time intelligence, and interactive visualizations to support revenue management and business decision-making

# 📌 Project Overview

The Hotel Revenue Analytics Dashboard is a Power BI project developed to analyze hotel booking performance, revenue trends, customer behavior, and operational efficiency.
Using over 119,000 real hotel booking records, this project demonstrates how Business Intelligence can be applied to the hospitality and travel industries to support data-driven decision-making.
The dashboard provides a comprehensive view of hotel performance through industry-standard revenue management metrics and interactive visualizations.

# 🎯 Business Problem

Hotels face several revenue management challenges:

Understanding booking demand patterns
Monitoring occupancy performance
Measuring revenue generation efficiency
Identifying cancellation risks
Forecasting future demand
Evaluating customer booking behavior

Without proper analytics, hotels may struggle with:

Revenue leakage from cancellations
Poor pricing decisions
Low occupancy periods
Inefficient forecasting
Missed revenue opportunities

This dashboard addresses these challenges through a centralized reporting and analytics solution.

# 🎯 Project Objectives

The primary objectives of this project are:

Analyze hotel booking performance over time
Measure revenue generation using industry-standard KPIs
Evaluate occupancy and room utilization
Identify cancellation patterns
Understand customer booking behavior
Analyze booking lead times
Track revenue growth trends
Build an executive-level Business Intelligence dashboard

# 📊 Dataset Information
**Dataset**
Hotel Booking Demand Dataset

# Source:

**Kaggle - Hotel Booking Demand Dataset**

# Dataset Summary
**Attribute**	                                                 **Value**
Records	                                                        119,390,
Hotels	                                                        Resort Hotel & City Hotel,
Period	                                                        2015–2017,
Country	                                                        Portugal,
Format	                                                        CSV,
Features	                                                      32 Columns

# 🛠️ Tools & Technologies
**Power BI**
Data Modeling,
Power Query,
DAX,
Data Visualization
**DAX Functions Used**
CALCULATE(),
SUMX(),
FILTER(),
DIVIDE(),
AVERAGEX(),
DATESINPERIOD(),
SAMEPERIODLASTYEAR(),
DATEDIFF()
**Data Modeling**
Star Schema Design,
Fact and Dimension Tables,
Date Table,
Time Intelligence

# 🏗️ Data Model
**Fact Table**
hotel_bookings

**Key fields:**
ADR
Lead Time
Total Nights
Arrival Date
Cancellation Status
Revenue

**Dimension Tables**
**Date Dimension**
Year
Quarter
Month
Week
Day
**Market Dimension**
Market Segment
Distribution Channel
**Customer Dimension**
Customer Type
Country
Repeated Guest Status

# 📈 Key Metrics (KPIs)

1. **Total Revenue**
Measures total revenue generated from completed bookings.

Formula:
Total Revenue =
SUMX(
    FILTER(
        hotel_bookings,
        hotel_bookings[is_canceled] = 0
    ),
    hotel_bookings[adr] *
    hotel_bookings[TotalNights]
)

2. **ADR (Average Daily Rate)**
Average room rate earned per occupied room.

ADR =
AVERAGEX(
    FILTER(
        hotel_bookings,
        hotel_bookings[is_canceled] = 0
    ),
    hotel_bookings[adr]
)

3. **Occupancy Rate**
Percentage of available rooms occupied.

Occupancy Rate =
DIVIDE(
    Actual Occupied Room Nights,
    Available Room Nights
)

4. **RevPAR**
Revenue generated per available room.

RevPAR =
[ADR] * [Occupancy Rate]

5. **Cancellation Rate**
Percentage of bookings cancelled.

Cancellation Rate =
DIVIDE(
    Cancelled Bookings,
    Total Bookings
)

6. **Revenue YoY %**
Year-over-Year revenue growth.

Revenue YoY % =
VAR CurrentRevenue = [Total Revenue]
VAR PreviousRevenue =
CALCULATE(
    [Total Revenue],
    SAMEPERIODLASTYEAR(DateTable[Date])
)
RETURN
DIVIDE(
    CurrentRevenue - PreviousRevenue,
    PreviousRevenue
)

7. **Average Lead Time**
Average days between booking date and arrival.

Avg Lead Time =
AVERAGE(
    hotel_bookings[lead_time]
)

8. **ADR Rolling 3 Months**
Tracks ADR trend using a rolling 3-month average.

ADR Rolling 3M =
CALCULATE(
    [ADR],
    DATESINPERIOD(
        DateTable[Date],
        MAX(DateTable[Date]),
        -3,
        MONTH
    )
)
# 📊 Dashboard Components

**Executive KPI Section**
Total Revenue
ADR
RevPAR
Occupancy Rate
Cancellation Rate
Average Lead Time
**Revenue Analysis**
Revenue Over Time
Revenue by Market Segment
Revenue YoY Growth
**Occupancy Analysis**
Occupancy Heatmap
Occupancy Trends
**Booking Behavior Analysis**
Lead Time Distribution
Customer Segmentation
**Cancellation Analysis**
Cancellation Funnel
Cancellation Rate by Segment
**Revenue Performance**
ADR Trend
RevPAR Trend
ADR Rolling 3-Month Analysis

# 💡 Key Business Insights
**Revenue Performance**
Total revenue exceeded $25 million from completed bookings.
ADR remained stable around $100, indicating consistent pricing performance.
**Occupancy**
Average occupancy remained close to 46%, highlighting opportunities for improving room utilization.
**Booking Behavior**
Guests booked approximately 80 days in advance on average.
Longer lead times were associated with higher cancellation risk.
**Cancellations**
Approximately 37% of bookings were cancelled, representing a significant revenue management challenge.
**Hotel Performance**
City Hotel generated higher revenue due to stronger booking volume despite similar ADR levels.


# 🚀 Business Value

This dashboard enables hotel managers and revenue teams to:

1. Monitor revenue performance
2. Optimize pricing strategies
3. Improve occupancy rates
4. Reduce revenue loss from cancellations
5. Forecast future demand
6. Support strategic business decisions

# 📚 Skills Demonstrated

**Business Analysis**
KPI Definition,
Revenue Analytics,
Customer Segmentation,
Trend Analysis,
Business Insight Generation

**Power BI**
Data Modeling,
DAX Calculations,
Time Intelligence,
Dashboard Design,
Interactive Reporting

**Data Analytics**
Data Cleaning,
Data Transformation,
Exploratory Analysis,
Performance Monitoring

# 🏁 Conclusion

This project demonstrates how Business Intelligence can be leveraged to solve real-world revenue management challenges in the hospitality industry. By combining data modeling, advanced DAX calculations, and executive-level dashboard design, the solution transforms raw booking data into actionable insights that support revenue optimization, occupancy management, and strategic decision-making.

The dashboard reflects the type of analytics commonly used by hospitality and travel organizations to improve business performance and drive data-informed decisions.


# 👩‍💻 Author

**Kritika Shotriya**
Business Analyst | Data Analyst | Business Intelligence Analyst | Power BI Analyst
GitHub: https://github.com/kritikashotriya16 
LinkedIn: https://www.linkedin.com/in/kritikashotriya16

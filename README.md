# uber-trip-analysis-powerbi
Power BI dashboard turning Uber trip data into insights on booking trends, revenue, trip efficiency, and pickup/drop-off demand to support data-driven decisions

Uber Trip Analysis | Power BI Dashboard

An interactive three-page Power BI report analysing Uber trip data (June 2026) to uncover insights into booking trends, revenue, trip efficiency, and location demand, helping stakeholders make data-driven decisions.

Designed & developed by: Glenn Tibane

Business Requirement

Analyse Uber trip data to gain insights into booking trends, revenue, and trip efficiency, with the goal of:

Identifying trends in ride bookings and revenue generation
Analysing trip efficiency in terms of distance and duration
Comparing booking values and trip patterns across different time periods
Providing insights to optimise pricing models and improve customer satisfaction
Key Metrics (KPIs)
KPI	Question it answers	Value
Total Bookings	How many trips were booked?	103.7K
Total Booking Value	What revenue did bookings generate?	$1.6M
Avg Booking Value	What is the average revenue per booking?	15.0
Total Trip Distance	How far did all trips cover?	349K miles
Avg Trip Distance	How far does a customer travel per trip?	3 miles
Avg Trip Time	How long is the average trip?	16 min
Report Pages

1. Overview Analysis
Measure selector (disconnected table) switching charts between Total Bookings, Total Booking Value, and Total Trip Distance
Breakdown by Payment Type and by Trip Type (Day/Night), with dynamic titles and tooltips
Vehicle Type Analysis grid with conditional formatting, sorting, and filtering
Total Bookings by Day trend to spot peak and off-peak days
Location Analysis: most frequent pickup point, most frequent drop-off point (via an inactive relationship activated in DAX), farthest trip, top 5 locations by bookings, and most preferred vehicle per pickup location
Date and City slicers, plus a Clear Filters button and a Data Details bookmark

3. Time Analysis

A global dynamic measure drives every visual on the page:

Pickup time (10-minute intervals): area chart for peak and off-peak demand
Day name: line chart for weekday vs weekend demand
Hour vs day of week: heatmap matrix (hours 0-23 by Mon-Sun)

3. Details
Grid table with key trip fields
Drill-through from other pages' visuals to the underlying records
"View Full Data" bookmark to toggle between filtered and full data
Key Insights

Fill these in from your own findings, for example:

UberX is the most booked vehicle type (~38.7K bookings)
Most frequent pickup point: Penn Station/Madison Sq
Most frequent drop-off point: Upper East Side North
(Add peak hours, busiest weekday, day vs night split, payment mix, etc.)
Power BI Techniques Used
Disconnected table + SWITCH measure for a dynamic measure selector
Dynamic chart titles
Inactive relationship activated with USERELATIONSHIP
Time intelligence and custom time-bucket columns (10-minute intervals)
Conditional formatting, tooltips, and drill-through pages
Bookmarks and buttons for navigation and slicer reset
Tools

Power BI Desktop, DAX, Power Query

Data Source

[Add where the dataset came from, number of rows, and time range (2026/06/01 to 2026/06/30).]

Repository Structure
uber-trip-analysis-powerbi/
├── README.md
├── Uber_Trip_Analysis.pbix
├── Problem_Statement.docx
├── data/
└── screenshots/
    └── overview.png
How to Use
Download Uber_Trip_Analysis.pbix
Open it in Power BI Desktop
Use the left-hand navigation to move between pages, and the slicers to filter by date and city
Author

Glenn Tibane

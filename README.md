# Uber Trip Analysis | Power BI Dashboard

An interactive three-page Power BI report analysing Uber trip data (June 2024) to uncover insights into booking trends, revenue, trip efficiency, and location demand, helping stakeholders make data-driven decisions.

**Designed & developed by:** Glenn Tibane

## Dashboard Preview

![Uber Trip Analysis Dashboard](screenshots/overview.png)

## Business Requirement

Analyse Uber trip data to gain insights into booking trends, revenue, and trip efficiency, with the goal of:

- Identifying trends in ride bookings and revenue generation
- Analysing trip efficiency in terms of distance and duration
- Comparing booking values and trip patterns across different time periods
- Providing insights to optimise pricing models and improve customer satisfaction

## Key Metrics (KPIs)

| KPI | Question it answers | Value |
|---|---|---|
| Total Bookings | How many trips were booked? | 103.7K |
| Total Booking Value | What revenue did bookings generate? | $1.6M |
| Avg Booking Value | What is the average revenue per booking? | 15.0 |
| Total Trip Distance | How far did all trips cover? | 349K miles |
| Avg Trip Distance | How far does a customer travel per trip? | 3 miles |
| Avg Trip Time | How long is the average trip? | 16 min |

## Report Pages

### 1. Overview Analysis
- **Measure selector** (disconnected table) switching charts between Total Bookings, Total Booking Value, and Total Trip Distance
- Breakdown **by Payment Type** and **by Trip Type (Day/Night)**, with dynamic titles and tooltips
- **Vehicle Type Analysis** grid with conditional formatting, sorting, and filtering
- **Total Bookings by Day** trend to spot peak and off-peak days
- **Location Analysis:** most frequent pickup point, most frequent drop-off point (via an inactive relationship activated in DAX), farthest trip, top 5 locations by bookings, and most preferred vehicle per pickup location
- Date and City slicers, plus a Clear Filters button and a Data Details bookmark

### 2. Time Analysis
A global dynamic measure drives every visual on the page:
- **Pickup time (10-minute intervals):** area chart for peak and off-peak demand
- **Day name:** line chart for weekday vs weekend demand
- **Hour vs day of week:** heatmap matrix (hours 0-23 by Mon-Sun)

### 3. Details
- Grid table with key trip fields
- **Drill-through** from other pages' visuals to the underlying records
- **"View Full Data"** bookmark to toggle between filtered and full data

## Key Insights

> Fill these in from your own findings, for example:

- UberX is the most booked vehicle type (~38.7K bookings)
- Most frequent pickup point: Penn Station/Madison Sq
- Most frequent drop-off point: Upper East Side North
- *(Add peak hours, busiest weekday, day vs night split, payment mix, etc.)*

## Power BI Techniques Used

- Disconnected table + `SWITCH` measure for a dynamic measure selector
- Dynamic chart titles
- Inactive relationship activated with `USERELATIONSHIP`
- Time intelligence and custom time-bucket columns (10-minute intervals)
- Conditional formatting, tooltips, and drill-through pages
- Bookmarks and buttons for navigation and slicer reset

## Tools

Power BI Desktop, DAX, Power Query

## Data Source

The report is built from two Excel files:

| File | Description | Size |
|---|---|---|
| `Uber_Trip_Details.xlsx` | Trip-level records for June 2024 (2024/06/01 to 2024/06/30) | 103,729 trips |
| `Location_Table.xlsx` | Lookup table mapping location IDs to location names and cities | 265 locations |

**Trip Details fields:** Trip ID, Pickup Time, Drop Off Time, passenger_count, trip_distance, PULocationID, DOLocationID, fare_amount, Surge Fee, Vehicle, Payment_type

**Location Table fields:** LocationID, Location, City

**Data model:** `PULocationID` (pickup) and `DOLocationID` (drop-off) both relate to `LocationID` in the Location Table. One relationship is active and the other is inactive, and is activated in DAX where needed.

**Categories:** 5 vehicle types (UberX, Uber Black, Uber Comfort, Uber Green, UberXL) and 4 payment types (Uber Pay, Cash, Amazon Pay, Google Pay).

## Repository Structure

```
uber-trip-analysis-powerbi/
├── README.md
├── Uber_Trip_Analysis.pbix
├── Problem_Statement.docx
├── data/
│   ├── Uber_Trip_Details.xlsx
│   └── Location_Table.xlsx
└── screenshots/
    └── overview.png
```

## How to Use

1. Download `Uber_Trip_Analysis.pbix`
2. Open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/)
3. Use the left-hand navigation to move between pages, and the slicers to filter by date and city

## Author

**Glenn Tibane**

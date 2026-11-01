# HOTEL CANCELLATION & REVENUE IMPACT ANALYSIS 

## Project Overview
This project is a five-page Power BI report that examines hotel booking cancellations and their estimated impact on revenue. The goal is to understand which guest groups and booking conditions are associated with higher cancellation rates, and how much potential accommodation revenue is estimated to be lost to cancellations.  
The report moves from a general view of bookings and guest profiles to the financial impact of cancellations, then to the factors associated with cancellation rates such as lead time, stay length, market segment and special requests. Key findings, recommendations and data limitations are summarized on the final page. All findings are observed patterns in the data and should not be read as proof of causation.

## Power BI Project 
### Hotel Bookings Overview
![Hotel Bookings Overview](IMAGES/1.HotelBookingsOverview.png)

### Guest Analysis 
![Guest Analysis](IMAGES/2.GuestAnalysis.png)

### Cancellation Revenue Impact 
![Cancellation Revenue Impact](IMAGES/3.CancellationRevenueImpact.png)

### Cancellation Rate Analysis
![Cancellation Rate Analysis](IMAGES/4.CancellationRateAnalysis.png)

### Key Findings
![Key Findings](IMAGES/5.KeyFindings.png)

## Summary of Findings
- Revenue impact: Canceled bookings make up 27% of all bookings but 33% of Potential Estimated Revenue, suggesting that canceled bookings tend to have a higher estimated value than average.
- Cancellation trends: Cancellation rates tend to be higher for longer lead times and lower for bookings with more special requests.
- Customer value: Couples account for the highest total revenue in both hotels, which coincides with their larger booking volume, while Adult Groups and Families show higher average revenue per booking.
  
## Recommendations
- Lead-time-based risk management: Bookings could be classified into lead time risk levels. Pre-arrival confirmation messages may help for bookings made 31–180 days ahead, and flexible date modification options could be considered for bookings made 181 or more days ahead.
- Post-booking customer engagement: Maintaining communication with guests after booking may help strengthen engagement and reduce cancellations, and could be tested on a small group.
- Cancellation reasons analysis: Surveys with Family and Adult Group guests could help identify the factors associated with their higher cancellation rates.

## Dataset Information 
This project uses the Hotel Booking Demand Dataset.

- Dataset: https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand
- License: CC BY 4.0 (Creative Commons Attribution 4.0 International)
- Original authors: Nuno Antonio, Ana Almeida, and Luis Nunes
- Dataset size: 119,390 records
- Period covered: July 2015 – August 2017
- Hotel types: City Hotel and Resort Hotel

## Data Preparation  
After cleaning, 87,011 bookings were used in the analysis (23,928 canceled).  
Cleaning steps:  
- Duplicate records were removed.
- Values stored as the text “NULL” were converted to actual null values using find and replace.
- Null values in the children column were replaced with 0.
- Null values in the agent and company columns were replaced with “Not Specified”.
- Data types were set for all columns.

Fields derived in Power BI:
- Arrival Date
- Potential Estimated Revenue
- Guest Group (Single Adult, Couple, Adult Group, Family)
- Lead Time Group
- Special Requests 

Key measures: Total Bookings, Cancellation Rate, Avg Daily Rate, Estimated Revenue, Estimated Lost Revenue, Revenue Loss Rate, Avg Loss per Cancellation, Avg Revenue per Booking and Repeated Guest Ratio.

## Tools 
- Power BI
- Power Query
- DAX

## Limitations 
- Data period: 2015 and 2017 are incomplete years, so year-to-year comparisons should be interpreted with caution.
- Estimated revenue: The dataset has no revenue column. Estimated Revenue is calculated as Average Daily Rate (ADR) × nights stayed for non-canceled bookings, and Estimated Lost Revenue as ADR × reserved nights for canceled bookings. Potential Estimated Revenue is the sum of the two. All three represent accommodation revenue only; additional spending is not available, and the loss estimate does not account for rooms resold after a cancellation.
- ADR: It is calculated from non-canceled bookings with non-zero ADR, excluding the “Complementary” market segment.
- Deposits: Only about 1,000 of 87,011 bookings have deposit data, so deposit types are excluded from the cancellation analysis and revenue estimates.
- Guest group: The grouping is derived, and the 385 bookings with no recorded adult count are classified as Family.
- Small groups: In the Cancellation Revenue Impact matrix, cells with fewer than 50 canceled bookings are hidden to reduce the risk of misleading averages.
- Observational findings: All results describe patterns in the data and do not establish causation.

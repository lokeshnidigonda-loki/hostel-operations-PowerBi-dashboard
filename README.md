🏨 Hostel Operations & Financial Performance Dashboard

A clean, modern 3-page Power BI dashboard designed to help hostel wardens, administrative staff, and managers track monthly revenues, analyze room occupancy rates, and optimize operational spend.

📊 Dashboard Pages

1. Money Page (Financial Performance)

Tracks monthly rent collections, calculates operational profit margins, and flags active rent defaulters in soft red alert formatting.

2. Room Page (Occupancy Analytics)

Analyzes space utilization using a target-calibrated speedometer gauge and a mathematically correct donut chart comparing occupied vs. vacant beds.

3. Expenses Page (Operational Spend)

Aggregates operating costs across food, utility bills, maintenance, and staff salaries, matching category colors across all visuals.

🛠️ Data Modeling (Star Schema)

This project is built using a highly efficient relational Star Schema to model historical hostel operations from February 2026 to July 2026:

Fact Tables (Transactions & Logs):

Fact_Rent (Monthly rent collection ledgers)

Fact_Expenses (Operational costs like food, utilities, and salaries)

Fact_Mess_Attendance (Daily student dining attendance logs)

Dimension Tables (Lookup Tables):

Dim_Members (Resident attributes and Active/Left status)

Dim_Rooms (Room numbers, sharing sizes, and AC/Non-AC types)

Dim_Month (Master calendar index for clean date filtering)

✍️ Key DAX Calculations Used

To keep calculations accurate, custom DAX measures were written instead of using raw columns:

1. Occupancy Rate %

Occupancy Rate % = DIVIDE([Beds Occupied], SUM(Dim_Rooms[Total_Beds]), 0)


2. Outstanding Rent (Unpaid Balances)

Calculates exact outstanding liabilities to spot revenue leaks instantly:

Outstanding Rent = SUM(Fact_Rent[Rent_Due]) - SUM(Fact_Rent[Amount_Paid])


📦 How to View this Project

Download the HostelPowerBi.pbix file from this repositorys.

Install Power BI Desktop (free).

Open the downloaded .pbix file to interact with the slicers, cross-filtering, and visual relationship

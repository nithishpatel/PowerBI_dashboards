# PowerBI_dashboards

**Routines Activation Dashboard:**

**Project overview**
The Routines Activation Power BI solution monitors how consistently operational “routines” are being activated across the full customer lifecycle, including Sales, Field Services, 7‑Day Visits, Collections, Customer Care, and Customer Service.
The report is designed for senior operations and commercial leaders who need a single view of activation rate, volume, and routine usage by country, customer type, and branch to drive performance management and process compliance.​

**Data sources and integration**
This solution brings together data from three enterprise systems: a PostgreSQL operational database, SharePoint files (ad‑hoc and manually curated logs), and Snowflake for centralised, high‑volume datasets.​
Using Power Query, the raw tables (Sales_data, Branches_info, IE_Branches_info, CUS01_CUSTOMER, Country, Customer_type, FS, Tickets, CC_agents, etc.) are cleaned, merged, and conformed to produce a consistent set of dimension and fact tables, including shared keys for customer, branch, and date to support cross‑department analysis.​

**Data modelling and date intelligence**
The model follows a star schema, with a single central Date table driving all departmental fact tables (Sales, Field Services routines, Collections, 7‑Day Visits, Tickets, Scheduled Services, etc.), which aligns with performance and best‑practice guidance for Power BI.​
The Date dimension includes period attributes and time‑intelligence flags (week, month, quarter, year, current vs previous period), enabling consistent calculations of activation rates by date, 7‑day visit windows, and trend analysis across every page in the report.​

**Business logic and DAX measures**
Core KPIs are implemented as reusable DAX measures rather than duplicated columns, including: total interactions (sales, services, visits, or tickets), routines activated, and activation rate per department.​
Activation rate is defined as routines activated ÷ eligible interactions, and all measures are fully filter‑aware so that changing country (UK vs Ireland), customer type (Residential vs Business), date range, or branch context dynamically recalculates the gauges, cards, and charts.​

**Advanced navigation and UX design**
The overview page provides a high‑level snapshot of activation performance for each department, with consistent gauges and KPI cards to make cross‑functional comparison easy for executives.
Interactive icon‑based bookmarks allow users to toggle between UK and Ireland data via flag icons and to switch between Residential and Business customers via dedicated icons, creating an app‑like experience instead of cluttered slicers.​

Clicking on the Sales tile navigates to a dedicated Sales Overview page (and similarly structured pages for 7‑Day Visits, Field Services, and Customer Care), using bookmarks and buttons for seamless page navigation.​
The Sales deep‑dive includes:

KPI cards for Total Sales, Routines Activated, Activation Rate.

Routines by branch bar charts showing how many routines are activated per location.

Sales by branch ranking to highlight high‑volume sites.

An Activation rate by Date time‑series visual for short‑term trend monitoring.

A detailed “Sales by routine flag” table listing installations, routine names, dates, and activation flags to support root‑cause analysis and coaching at record level.

Performance optimisation choices
The report is built with performance in mind, following enterprise optimisation practices:

Lean star schema with only required columns and rows retained, and text fields reduced where possible to improve VertiPaq compression and query speed.​

Preference for Power Query transformations (merges, derived columns, type conversions) instead of calculated columns, to push heavy work to the data refresh step and preserve report responsiveness.​

Use of import mode for core fact tables with appropriate aggregations rather than excessive DirectQuery, balancing freshness and speed; Row‑level filters and incremental refresh can be applied where necessary as data volume grows.​

Controlled visual density on each page (limited number of visuals and interactions) so that executives get a fast, focused experience without overloading the report canvas.​

**Business impact and transferable skills**
This project demonstrates the ability to translate a complex operational process (multi‑department routine activation) into a clear analytical model with consistent KPIs, driven from disparate sources (PostgreSQL, SharePoint, Snowflake).​
It highlights advanced Power BI capabilities: enterprise‑grade data modelling, central date table and time intelligence, DAX measure design, bookmark‑based navigation, and performance tuning—all directly applicable to sales, service, and operations reporting in real‑world organisations.

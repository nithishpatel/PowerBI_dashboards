This repository showcases end‑to‑end ownership of enterprise‑grade Power BI solutions, from data modelling and DAX engineering to UX design, navigation, and performance optimisation.

**Data engineering and modelling**

Built star‑schema models with conformed dimensions (e.g., central Date table, Customer, Branch, Country, Product, Contract) feeding multiple subject‑area reports (sales, operations, collections, service, invoicing).

Designed a central Date table with full time‑intelligence (calendar attributes, fiscal flags, current/previous period markers, rolling 7‑day and 12‑month logic) and disabled auto date/time to keep models lean and consistent.

Integrated data from PostgreSQL, SharePoint and Snowflake, using Power Query for type handling, conditional logic, merges, and surrogate key creation so that business tables from different systems join cleanly.

Applied modelling best practices: only necessary columns loaded, numeric encoding of categories, separation of measures from columns, and clear folder structures for maintainability.

**DAX, metrics, and business logic**

Authored reusable DAX measure layers for KPIs across domains: activation rate, ticket backlog, write‑off amount, recovery rate, margin %, contract status %, and portfolio‑level debt indicators.

Implemented filter‑aware calculations so metrics respond correctly to country, segment, date, department, product, and salesperson context without report‑level hacks.

Built Top‑N logic (e.g., Top 5 sellers, Top 5 resellers, top branches) combined with dynamic ranking tables for both regional and global views.

Used field parameters to let users switch interactively between metrics (CA, margin, target attainment, etc.) and dimensions while reusing the same visuals, reducing complexity and improving performance.

**Advanced UX, navigation, and storytelling**

Designed multiple reports as app‑like experiences using bookmarks, buttons, and custom navigation bars (Overview/Details tabs, department tiles, icon‑based navigation).

Created bookmark‑driven drill experiences: from high‑level overviews into deep‑dive pages for Sales, Field Services, 7‑Day Visits, Customer Care, Contracts, and Collections, all preserving the user’s filter context.

Implemented pop‑out filter panels and icon‑based segment selectors (e.g., UK vs Ireland, Residential vs Business) to keep the canvas clean while still offering powerful slicing.

Used consistent visual templates and layout patterns (KPI cards, gauges, trend lines, “Excel‑like” matrices, small multiples) so executives can scan and compare performance across functions in seconds.

**Performance optimisation and governance**

Optimised reports by minimising visual count per page, removing unused columns, and preferring measures over calculated columns to reduce model size.

Pushed heavy transformations to Power Query and source systems, keeping the semantic model focussed on calculations rather than ETL.

Used import mode with incremental refresh and aggregations (where applicable) to balance freshness and query speed on operational and finance datasets.

Followed a clear naming convention for tables, measures, and display folders, making the models production‑ready and easy for other analysts to extend.

**Business domains covered**

Across the projects in this repository, these techniques are applied to real business scenarios:

Service routines activation across Sales, Field Services, Collections, Customer Care, Customer Service, and 7‑Day Visits.

Finance collections for non‑active B2C debtors, including aging, write‑off candidates (>6 months), and recovery rates by unpaid invoices.

Contracts and invoicing pipelines from installation to invoiced/solved status with ticket‑backlog monitoring.

Global sales performance with KPI L12M, regional and global rankings, category mix, and top‑seller/top‑reseller analysis.

Together, these dashboards demonstrate the ability to take messy, multi‑source operational data, engineer robust semantic models, encode complex business logic in DAX, and deliver fast, intuitive, executive‑ready Power BI experiences.

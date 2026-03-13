# Ukraine Road Safety & Vehicle Market Analysis

## Overview
This project is a comprehensive, end-to-end Business Intelligence and Data Warehousing solution designed to analyze the transportation sector in Ukraine. The system processes over 6 million transactional records to evaluate vehicle registration dynamics, road accident hotspots, and stolen vehicle statistics.

## Data Sources
The data warehouse integrates four key open-data sources:
* **Vehicle Registry (MIA of Ukraine):** Over 6 million records of vehicle registration operations from 2022 to 2024.
* **Accident-Prone Road Sections:** 2024 aggregated data on dangerous highway segments from the Agency for Restoration and Development of Infrastructure.
* **Wanted Vehicles Database (National Police):** Records of illegal vehicle seizures from 2017 to 2023.
* **KOATUU Classifier:** Official administrative-territorial dictionary used for precise geocoding and mapping.

## Architecture & Data Engineering (PostgreSQL)
* **Data Modeling:** Designed and implemented a complex **Galaxy Schema** architecture, featuring a Staging zone for raw data and a normalized Core warehouse. 
* **ETL Pipelines:** Developed robust PL/pgSQL procedures to extract, cleanse, and enrich data, including dynamic date parsing and geographic mapping via the KOATUU dictionary.
* **Performance Optimization:** Optimized database queries for processing millions of rows by implementing B-Tree indexing, Common Table Expressions (CTEs), and `ON CONFLICT DO NOTHING` logic to avoid inefficient nested loops.
* **Historical Tracking:** Implemented Slowly Changing Dimensions (SCD Type 2) to accurately track historical changes in vehicle brand data.

## BI Dashboard & Visualizations (Power BI)
* **Unified Analytics:** Connected multiple independent fact tables through shared dimensions to enable cross-process analysis within a single interactive ecosystem.
* **Geospatial Analysis:** Built interactive cartograms with gradient conditional formatting to visualize the geographic distribution of road accidents across regions.
* **Drill-Through Reporting:** Implemented advanced drill-through mechanics, allowing users to navigate from high-level regional accident summaries down to detailed statistics for specific highways.
* **Dynamic Forecasting:** Developed predictive analytics using DAX-based "What-if" parameters to model and forecast future vehicle registration trends based on user input.

# Methodology

## 1. Define the Analysis

The project started by identifying the key questions the incident data should answer rather than selecting visuals first.

The analysis focused on three main areas:

- **Overall Incident Demand** - understanding incident volumes, status, priority and changes in demand over time.
- **Service Demand** - identifying which affected services generate the greatest number of incidents and where demand is most concentrated.
- **Callers & Teams** - understanding where incidents originate and how workload is distributed across callers and assignment groups.

These areas were used to structure the Power BI report into three separate analytical pages.

## 2. Data Preparation

The original analysis was developed using approximately 7,910 ServiceNow incident records from 2026.

Before building the report, the data was reviewed and prepared for analysis. This included:

- Validating data types, particularly incident date fields.
- Checking for blank and inconsistent values.
- Standardising fields used for grouping and filtering.
- Checking for duplicate records where appropriate.
- Validating row counts following transformation.
- Reviewing fields that could contain confidential or personally identifiable information.

Power Query was used to prepare and transform the data before loading it into the Power BI model.

## 3. KPI Development

DAX measures were created to support consistent calculations throughout the report.

The measures were designed to support analysis of areas including:

- Total incident volume.
- Open and closed incidents.
- Closure rate.
- High-priority incidents.
- Incident volume by affected service.
- Contribution of high-volume services to overall demand.

Using measures allowed the calculations to respond dynamically to the filters and slicers applied throughout the report.

Representative measures are documented separately in `dax/measures.md`.

## 4. Report Design

The Power BI report was separated into three pages to keep the analysis focused and avoid overcrowding a single dashboard.

### Overview

The *Overview* page provides a high-level view of incident activity. Headline KPIs are combined with monthly trend analysis to show the overall level of support demand and how incident volumes change throughout the reporting period.

### Service Demand

The *Service Demand* page analyses incidents by affected service.

The page is designed to identify which services generate the greatest incident demand and how much of overall demand is concentrated within the highest-volume services.

This provides a starting point for identifying services that may require further investigation.

### Callers & Teams

The *Callers & Teams* page examines where incidents originate and how support workload is distributed.

Caller analysis identifies anonymised users associated with higher incident volumes, while assignment group analysis shows where workload is concentrated across support teams. Priority analysis provides additional context around the incidents being handled.

## 5. Analytical Approach

The dashboard uses descriptive analysis to identify patterns in operational support data.

High incident volume is treated as an indicator for further investigation rather than evidence of root cause.

For example, a service with a high number of incidents may also support a larger number of users or transactions. Similarly, a caller associated with a high number of incidents may interact with particular systems more frequently as part of normal business activity.

For this reason, the analysis focuses on identifying **where support demand is concentrated** and uses those findings as a starting point for deeper investigation.

## 6. Data Validation

Several checks were used throughout the analysis to make sure the report remained consistent with the underlying data.

These included:

- Comparing Power BI row counts against the source dataset.
- Checking the effect of report and page-level filters.
- Validating KPI values after applying slicers.
- Reviewing category values used within charts and tables.
- Checking calculations when filters were removed or changed.

This was particularly important because slicers and filter context can change headline KPI values without changing the underlying dataset.

## 7. Data Confidentiality

The original ServiceNow dataset is not included in the public repository.

The portfolio version uses anonymised dashboard screenshots and synthetic sample data so that the analytical approach can be demonstrated without exposing organisational information.

Information such as employee details, incident identifiers, confidential ticket information and internal system details has therefore been excluded from the public version of the project.

## 8. Further Analysis

The current dashboard provides a foundation for additional analysis.

Future development could include:

- Resolution-time analysis by priority and affected service.
- Recurring incident and issue-category analysis.
- Comparison of incident volumes against application user populations.
- Repeat-incident analysis.
- Longer-term trend and seasonality analysis using multiple years of data.
- Investigation of whether knowledge articles, process changes or automation could reduce recurring support demand.

These additions would allow the analysis to move beyond identifying where demand is concentrated towards understanding **why the demand occurs and how it could potentially be reduced**.
